---
title: コントローラー動作のガイドライン
permalink: controller-behavior-guidelines.html
sidebar: firetv_ja
product: Fire TV
toc-style: kramdown
---

Amazon Fire TVプラットフォーム向けのアプリを開発する際、各種コントローラーからの入力に対応させることができます。コントローラーには、Amazon Fire TVリモコンと音声認識リモコン、Amazon Fire TVゲームコントローラー、Bluetooth HIDゲームパッドプロファイルをサポートするその他のコントローラーが含まれます。


アプリにコントローラー入力を実装するには、「[リモコン入力][amazon-fire-tv-remote-input]」と「[ゲームコントローラー入力][amazon-fire-game-controller-input]」に記載されているモーションイベントと入力イベントを使用します。

このページでは、同じアプリの機能をさまざまな種類のコントローラーで設計する際の、推奨事項について説明します。以下のガイドラインは、Amazon Fire TV用アプリを公開するために必要な要件ではありません。開発者は、アプリに最も合う方法でコントローラー入力を設計することができます。ただし、他のコントローラー、アプリ、ゲームでも一貫したユーザーエクスペリエンスを提供するために、これらのガイドラインに従うことをおすすめします。

{% include note.html content="[マイク] ボタンを除けば、すべてのFire TVリモコンの動作は同じです。Fire TVリモコンに関するこのドキュメントのガイドラインは、Fire TV音声認識リモコンにも適用されます。" %}

* TOC
{:toc}

## コア動作

<table>
<colgroup>
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="40%" />
</colgroup>
  <thead>
    <tr>
      <th>アクション</th>
      <th>Amazon Fire TVリモコンのボタン</th>
      <th>Amazon Fire TVゲームコントローラーのボタン</th>
      <th>その他のゲームコントローラーのボタン</th>
      <th>動作</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ホーム</td>
      <td>ホーム</td>
      <td>ホーム</td>
      <td>ホーム (存在する場合) </td>
      <td>これはシステムイベントで、アプリではキャプチャできません。このボタンを押すと、ホームに戻ります。Amazonアプリストアでゲームに分類されるアプリの場合は、GameCircleオーバーレイまたは [Game Paused] 画面が表示されます。もう一度 [ホーム] ボタンを押すと、ホームに戻ります。<br /><br /> 予期せずホームに戻った場合にアプリまたはゲームの状態を保持するには、<a href="http://developer.android.com/reference/android/app/Activity.html#onPause()"><code>onPause()</code></a> を実装します。アプリを続きから再開できるようにするには、<a href="http://developer.android.com/reference/android/app/Activity.html#onResume()"><code>onResume()</code></a> を実装します。<br /><br />オーディオアプリの場合、<a href="http://developer.android.com/training/managing-audio/audio-focus.html">オーディオフォーカス</a>をリクエストして、バックグラウンドで再生を続けることができます。</td>
    </tr>
    <tr>
      <td>戻る</td>
      <td>バック</td>
      <td>バック</td>
      <td>B</td>
      <td>直前の操作または画面 (アクティビティ) に戻るか、現在の操作またはプロンプトを取り消します。<br /><br />確認ダイアログを表示するには、このイベントをキャプチャします。たとえば、アプリのメイン画面に [終了しますか?] ダイアログを表示するには、[バック] をキャプチャします。</td>
    </tr>
    <tr>
      <td>メニュー</td>
      <td>メニュー</td>
      <td>メニュー</td>
      <td>Y</td>
      <td>Androidの標準コンテキストメニュー (<a href="http://developer.android.com/guide/topics/ui/menus.html#options-menu">OptionsMenu</a>) が起動されます。<br /><br />独自のメニューを提供するか、他の目的に使う場合は、このイベントをキャプチャします。提供するメニューに 1 つしかオプションがない場合は、[メニュー] ボタンをそのオプションの切り替えボタンとして使用できます。<br /><br />メディアアプリでは、[メニュー] ボタンを使って再生パネルを表示または非表示にできます。</td>
    </tr>
    <tr>
      <td>検索</td>
      <td>マイク (音声認識リモコンのみ)</td>
      <td>該当なし</td>
      <td>該当なし</td>
      <td>これはシステムイベントで、アプリではキャプチャできません。このボタンを押すと、音声検索が起動されます。<br /><br />音声検索の起動時にアプリまたはゲームの状態を保持するには<a href="http://developer.android.com/reference/android/app/Activity.html#onPause()"><code>onPause()</code></a> を実装し、検索完了後にアプリやゲームを続行できるようにするには<a href="http://developer.android.com/reference/android/app/Activity.html#onResume()"><code>onResume()</code></a> を実装します。<br /><br />オーディオアプリでは、音声検索の起動中は、再生を一時停止するか、音量を小さくします。<br /><br />ビデオアプリでは、音声検索の起動中は、音声をミュートするか、再生を一時停止します。</td>
    </tr>
    <tr>
      <td>GameCircle</td>
      <td>該当なし</td>
      <td>GameCircle</td>
      <td>該当なし</td>
      <td>これはシステムイベントで、アプリではキャプチャできません。このボタンを押すと、GameCircleオーバーレイ (GameCircleをサポートしているゲームの場合)、または [Game Paused] ダイアログ (GameCircleをサポートしていないゲームの場合) が表示されるか、ランチャーの [Games] ページに戻ります (他のすべてのアプリの場合)。<br /><br /> <strong>注意:</strong> サイドロードされたアプリは、GameCircleを実装していても必ずランチャーの [Games] ページに戻ります。GameCircleの正しい動作を示すのは、Amazonアプリストアに申請されたアプリだけです。アプリを申請する前に、<a href="https://developer.amazon.com/public/resources/development-tools/live-app-testing">ライブアプリテスト</a>を使用してGameCircleの統合をテストできます。<br /><br /> [GameCircle] ボタンが押されたときにアプリまたはゲームの状態を保持するには、<a href="http://developer.android.com/reference/android/app/Activity.html#onPause()"> <code>onPause()</code></a> を実装します。ユーザーがゲームに戻ったときに続きから再開できるようにするには、<a href="http://developer.android.com/reference/android/app/Activity.html#onResume()">onResume()</a> を実装します。</td>
    </tr>
  </tbody>
</table>

## ナビゲーションと選択

次の表では、ユーザーインターフェースのナビゲーションと選択で推奨される動作について説明します。複数のボタンを表示するアイテムでは、すべてのボタンを対象にしてください。

<table>
<colgroup>
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="40%" />
<colgroup>
  <thead>
    <tr>
      <th>アクション</th>
      <th>Amazon Fire TVリモコンのボタン</th>
      <th>Amazon Fire TVゲームコントローラーのボタン</th>
      <th>その他のゲームコントローラーのボタン</th>
      <th>動作</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>選択/メインアクション</td>
      <td>D-pad (ナビゲーション) の [選択]</td>
      <td>A</td>
      <td>A</td>
      <td>フォーカスされたアイテムを選択するか、メニューオプションまたはプロンプトを確定するか、メインゲームアクションを実行します。</td>
    </tr>
    <tr>
      <td>キャンセル/戻る</td>
      <td>バック</td>
      <td>バック <br />B</td>
      <td>B</td>
      <td>現在の操作を取り消すか、直前の画面に戻ります。<br /><br />確認ダイアログ ("Are you sure you want to quit?") を表示するには、このアクションをインターセプトします。</td>
    </tr>
    <tr>
      <td>上<br />下<br />左<br />右</td>
      <td>D-pad</td>
      <td>D-pad (十字キー)<br />左アナログスティック</td>
      <td>D-pad (十字キー)<br />左アナログスティック</td>
      <td>入力フォーカスを該当する方向に移動します。<br /> <br />Amazon Fireゲームコントローラーやその他のゲームコントローラーでは、左アナログスティックがD-padと同じ動作をします。</td>
    </tr>
  </tbody>
</table>

## メディアの再生

次の表では、メディアの再生に関する推奨動作を説明します。次の点に注意してください。

* メディアを再生しないアプリや、アナログスティックまたはショルダーボタン (L1/R1) を使用するアプリの場合には、それらのボタンのイベントをキャプチャしないでください。他の機能にキャプチャすると、システムがバックグラウンドで再生しているメディアをコントロールできなくなる可能性があります。
* Unityなどのフレームワークはシステム経由で主要なイベントを渡す機能がサポートされていないため、これらのフレームワークを使用しているアプリの場合、この推奨を無視できます。
* アプリやゲームでこれらのボタンを他の目的のために使用する場合、GameCircleオーバーレイ (GameCircleボタン) から、またはFire TVランチャーで、システムメディアコントロールにアクセスできます。

<table>
<colgroup>
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="15%" />
<col width="25%" />
<colgroup>
  <thead>
    <tr>
      <th>アクション</th>
      <th>Amazon Fire TVリモコンのボタン</th>
      <th>Amazon Fire TVゲームコントローラーのボタン</th>
      <th>Amazon Fireゲームコントローラー (第 1 世代) のボタン</th>
      <th>その他のゲームコントローラーのボタン</th>
      <th>動作</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>再生/一時停止</td>
      <td>再生/一時停止</td>
      <td>A<br />左側/右側のアナログスティックの押し下げ</td>
      <td>再生/一時停止</td>
      <td>A</td>
      <td>メディアの再生と一時停止を切り替えます。</td>
    </tr>
    <tr>
      <td>早戻し</td>
      <td>早戻し<br />左 (D-pad)<br />L1ショルダーボタン</td>
      <td>L1ショルダーボタン</td>
      <td>早戻し<br />左 (D-pad)<br />L1ショルダーボタン</td>
      <td>左 (D-pad) <br />L1ショルダーボタン</td>
      <td>再生中のメディアコンテキストが早戻しされます。実際の動作はそれぞれのメディアによって異なります。ビデオなら再生位置の調整に、音楽なら直前のトラックに戻るために、スライドショーなら直前の写真に移動するために、このボタンを使用できます。</td>
    </tr>
    <tr>
      <td>早送り</td>
      <td>FF<br />右 (D-pad)<br />R1ショルダーボタン</td>
      <td>R1ショルダーボタン</td>
      <td>FF<br />右 (D-pad)<br />R1ショルダーボタン</td>
      <td>右 (D-pad)<br />R1ショルダーボタン</td>
      <td>再生中のメディアコンテキストが早送りされます。正確な動作はそれぞれのメディアによって異なります。ビデオなら再生位置の調整に、音楽なら次のトラックに進むために、スライドショーなら次の写真に移動するために、このボタンを使用できます。</td>
    </tr>
  </tbody>
</table>


## 音量制御

Amazon Fire TVでは、オーディオをAmazon Fire TVゲームコントローラーのヘッドホンジャックにストリーミングできます。オーディオ再生の音量制御は、左側/右側のトリガーボタン (L2/R2) を使用して行うことができます。音量制御はシステム機能であり、アプリの他のボタンにマップできません。

次の点に注意してください。

* これらのボタンを使用しないアプリまたはゲームの場合、それらの入力イベントをキャプチャしないでください。他の機能にキャプチャすると、ユーザーは音量をコントロールできなくなる可能性があります。
* アプリやゲームでこれらのボタンを他の目的のために使用する場合、GameCircleオーバーレイから、またはFire TVランチャーで、システム音量制御にアクセスできます。

<table>
<colgroup>
<col width="30%" />
<col width="70%" />
<col width="15%" />
</colgroup>
  <thead>
    <tr>
      <th>アクション</th>
      <th>Amazon Fire TVゲームコントローラーのボタン</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>音量 +</td>
      <td>L2トリガー </td>
    </tr>
    <tr>
      <td>音量 -</td>
      <td>R2トリガー </td>
    </tr>
  </tbody>
</table>

## ゲームプレイ

ゲームプレイのユーザーインターフェースはゲームによって大きく違いますが、基本的な推奨事項は次の表の通りです。


<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="30%" />
<col width="30%" />
</colgroup>
  <thead>
    <tr>
      <th>アクション</th>
      <th>Amazon Fire TVリモコンのボタン</th>
      <th>Amazon Fire TVゲームコントローラーのボタン</th>
      <th>その他のゲームコントローラーのボタン</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>プライマリゲームプレイアクション</td>
      <td>D-padの [選択]</td>
      <td>A</td>
      <td>A</td>
    </tr>
    <tr>
      <td>セカンダリゲームプレイアクション</td>
      <td>推奨なし</td>
      <td>B</td>
      <td>B</td>
    </tr>
  </tbody>
</table>


{% include links.html %}
