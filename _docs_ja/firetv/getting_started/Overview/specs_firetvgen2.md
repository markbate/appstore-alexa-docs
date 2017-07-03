<div class="subheading">メディアの仕様 (Fire TV、第 2 世代)</div>

<table class="grid">
   <colgroup>
      <col width="10%" />
      <col width="17%" />
      <col width="15%" />
      <col width="38%" />
   </colgroup>
   <thead>
      <tr class="header">
         <th>タイプ</th>
         <th>コーデック</th>
         <th>MIME type</th>
         <th>詳細</th>
      </tr>
   </thead>
   <tr>
        <td class="white" rowspan="6"><b>ビデオ</b></td>
        <td class="white">H.263</td>
        <td class="white">video/3gp</td>
        <td class="white">ハードウェアによる高速化: 最大WVGA (800 x 400)、30fps、6 Mbps、プロファイル 0 レベル 70</td>
     </tr>
     <tr>
        <td class="white">H.264</td>
        <td class="white">video/avc</td>
        <td class="white">ハードウェアによる高速化: 最大 1080p、30fps、20 Mbps、ハイプロファイル (最大レベル 4)</td>
     </tr>
     <tr>
        <td class="white">H.265 (HEVC)</td>
        <td class="white">video/mp4</td>
        <td class="white">ハードウェアによる高速化: 最大 3840x2160p (4K)、30 fps、25 Mbps、Main 10 プロファイル (レベル 5.0)、色空間 8 ビットおよび 10 ビット (入力のみ、出力は 8 ビット)</td>
     </tr>
     <tr>
        <td class="white">VP8</td>
        <td class="white">video/webm</td>
        <td class="white">ハードウェアによる高速化、プロファイル 0</td>
  </tr>
     <tr>
        <td class="white">VP9</td>
        <td class="white">video/webm</td>
        <td class="white">ハードウェアによる高速化: 最大Youtube 4K、プロファイル 0</td>
  </tr>
      <tr>
         <td class="white">MPEG-4</td>
         <td class="white">video/mp4v-es</td>
         <td class="white">最大 1080p、30fps、20 Mbps、アドバンスドシンプルプロファイル (レベル 5)</td>
      </tr>
   <tr>
      <td class="gray" rowspan="12"><b>オーディオ</b></td>
      <td class="gray">AAC-LC</td>
      <td class="gray">audio/mp4a-latm</td>
      <td class="gray">最大 96 kHz、6 チャネル、16 ビットおよび 24 ビット</td>
   </tr>
   <tr>
      <td class="gray">HE-AACv1 (AAC+)</td>
      <td class="gray">audio/mp4a-latm</td>
      <td class="gray">最大 96 kHz、6 チャネル、16 ビットおよび 24 ビット</td>
   </tr>
   <tr>
      <td class="gray">HE-AACv2 (拡張AAC+)</td>
      <td class="gray">audio/mp4a-latm</td>
      <td class="gray">最大 96 kHz、6 チャネル、16 ビットおよび 24 ビット</td>
   </tr>
   <tr>
      <td class="gray">AC3 (ドルビーデジタル)</td>
      <td class="gray">audio/ac3</td>
      <td class="gray">最大 48 kHz、6 チャネル、16 ビットおよび 24 ビット</td>
   </tr>
   <tr>
      <td class="gray">eAC3 (ドルビーデジタルプラス)</td>
      <td class="gray">audio/eac3</td>
      <td class="gray">最大 48 kHz、6 チャネル、16 ビットおよび 24 ビット</td>
   </tr>
   <tr>
      <td class="gray">FLAC</td>
      <td class="gray">audio/flac</td>
      <td class="gray">最大 48 kHz、2 チャネル、16 ビットと 24 ビット (24 ビットはディザなし)</td>
   </tr>
   <tr>
      <td class="gray">MIDI</td>
      <td class="gray">該当なし</td>
      <td class="gray">MIDI (タイプ 0 および 1)、DLS (バージョン 1 および 2)、XMF、およびモバイルXMF。着信音の形式: RTTTL/RTX、OTA、およびiMelody</td>
   </tr>
   <tr>
      <td class="gray">MP3</td>
      <td class="gray">audio/mp3</td>
      <td class="gray">最大 48 kHz、DSPに 2 チャネル (16 ビットおよび 24 ビット) およびソフトウェア (16 ビット)</td>
   </tr>
   <tr>
      <td class="gray">PCM/Wave</td>
      <td class="gray">該当なし</td>
      <td class="gray">最大 96 kHz、6 チャネル、16 ビットおよび 24 ビット</td>
   </tr>
   <tr>
      <td class="gray">Vorbis</td>
      <td class="gray">audio/vorbis</td>
      <td class="gray">Ogg (.ogg)<br/>Matroska (.mkv)</td>
   </tr>
      <tr>
      <td class="gray">AMR-NB</td>
      <td class="gray">audio/amr-web</td>
      <td class="gray"></td>
      </tr>
       <tr>
       <td class="gray">AMR-WB</td>
       <td class="gray">audio/3gpp</td>
       <td class="gray"></td>
       </tr>
   <tr>
           <td class="white"><b>DRM</b></td>
           <td class="white" colspan="2" markdown="span">Widevine Level 1 <br/> PlayReady Version 2.5 のみ</td>
           <td class="white" markdown="span">PlayReadyでサポートされるのは暗号化されたビデオだけです。オーディオはサポートされません。暗号化されたオーディオとビデオの両方を含むコンテンツを再生する必要がある場合は、[こちら](https://developer.amazon.com/appsandservices/support/contact/contact-us)から具体的なカスタマイズの詳細と手順をお問い合わせください。その他のDRMに関する情報は、実装する[メディアプレーヤー][fire-tv-media-players]によって異なります。</td>
     </tr>
   <tr>
      <td class="gray" rowspan="4"><b>画像</b></td>
      <td class="gray">JPEG</td>
      <td class="gray">該当なし</td>
      <td class="gray">ベースおよびプログレッシブ</td>
   </tr>
   <tr>
      <td class="gray">GIF</td>
      <td class="gray">該当なし</td>
      <td class="gray"></td>
   </tr>
   <tr>
      <td class="gray">PNG</td>
      <td class="gray">該当なし</td>
      <td class="gray"></td>
   </tr>
   <tr>
      <td class="gray">BMP</td>
      <td class="gray">該当なし</td>
      <td class="gray"></td>
   </tr>      
</table>

<div class="subheading">端末およびプラットフォームの仕様 (Fire TV、第 2 世代)</div>

<table class="grid">
   <colgroup>
      <col width="40%" />
      <col width="60%" />
   </colgroup>
  <thead>
    <tr>
      <th>端末の要素</th>
      <th>詳細</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>画面解像度 (px) とリフレッシュレート (Hz)</td>
      <td>3840 x 2160 (2160p / 4K) - 30Hz <br /> 
      1920 x 1080 (1080p) - 60Hz <br/> 
      1280 x 720 (720p) - 60Hz</td>
    </tr>
    <tr>
     <td>HDCP</td>
     <td>2.2</td>
   </tr>
    <tr>
      <td>密度 (dp)</td>
      <td>640 (2160p) <br /> 320 (1080p) <br /> 213 (720p)</td>
    </tr>
    <tr>
      <td>密度識別子</td>
      <td>xxxhdpi (2160p) <br /> xhdpi (1080p) <br /> tvdpi (720p)</td>
    </tr>
    <tr>
      <td>ストレージ</td>
      <td>8 GB</td>
    </tr>
    <tr>
      <td>RAM</td>
      <td>2 GB</td>
    </tr>
    <tr>
      <td>システムオンチップ (SoC) プラットフォーム</td>
      <td>MediaTek 8173C</td>
    </tr>
    <tr>
      <td>CPU</td>
      <td>Quad Core (最大 2GHzのDual Core ARM Cortex A72、最大 1.573 GhzのDual Core ARM Cortex A53)</td>
    </tr>
    <tr>
      <td>GPU</td>
      <td>PowerVR Rogue GX6250</td>
    </tr>
    <tr>
      <td>ネットワーキング: WiFi</td>
      <td>802.11 a/b/g/n/ac; 2x2 MIMO <br /> (2.4 GHzおよび 5.0 GHzデュアルバンド)</td>
    </tr>
    <tr>
      <td>ネットワーキング: イーサネット </td>
      <td>10/100Mbs</td>
    </tr>
    <tr>
      <td>Bluetooth</td>
      <td>Bluetooth 4.1、BTLE <br /> HID、HFP、SPPプロファイル</td>
    </tr>
    <tr>
      <td>USB</td>
      <td>USB 2.0 Type A (アクセサリおよびメディアストレージ)</td>
    </tr>
    <tr>
      <td>拡張可能ストレージ</td>
      <td markdown="span">最大 128 GBのMicroSD  <br/>(ストレージに関連したマニフェスト設定のベストプラクティスについては「[アプリのインストール場所の指定][specifying-installation-location]」を参照)</td>
    </tr>
    <tr>
      <td>端末のOS/プラットフォームソフトウェア</td>
      <td>Android 5.0 に基づく (API 22)</td>
    </tr>
    <tr>
      <td>位置情報サービス</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>前面カメラ</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>マイク</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>マルチタッチ</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>加速度計</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>コンパス</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>ジャイロスコープ</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>光センサー</td>
      <td>なし</td>
    </tr>
    <tr>
      <td>近接センサー</td>
      <td>なし</td>
    </tr>
    <tr>
      <td><code>android.os.Build.MANUFACTURER</code></td>
      <td markdown="span"><code>Amazon</code>。詳細については、「[Identifying Amazon Fire TV Devices][identifying-amazon-fire-tv-devices]」を参照してください。</td>
    </tr>
    <tr>
      <td><code>android.os.Build.MODEL</code></td>
      <td><code>AFTS</code> (Fire TV第 2 世代のみ) <br/> <code>AFT*</code> (すべてのFire TV端末)</td>
    </tr>
  </tbody>
</table>

<div class="subheading">OpenGLのプロパティと制限 (Fire TV、第 2 世代)</div>

<table class="grid">
   <colgroup>
      <col width="40%" />
      <col width="60%" />
   </colgroup>
  <thead>
    <tr>
      <th>アイテム</th>
      <th>詳細</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>OpenGLのバージョン</td>
      <td>OpenGL ES 3.0</td>
    </tr>
    <tr>
      <td><code>MAX_TEXTURE_SIZE</code></td>
      <td>8192</td>
    </tr>
    <tr>
      <td><code>MAX_CUBE_MAP_TEXTURE_SIZE</code></td>
      <td>8192</td>
    </tr>
    <tr>
      <td><code>MAX_RENDERBUFFER_SIZE</code></td>
      <td>8192</td>
    </tr>
    <tr>
      <td><code>MAX_VERTEX_TEXTURE_IMAGE_UNITS</code></td>
      <td>16</td>
    </tr>
    <tr>
      <td><code>MAX_TEXTURE_IMAGE_UNITS</code></td>
      <td>16</td>
    </tr>
    <tr>
      <td><code>MAX_COMBINED_TEXTURE_IMAGE_UNITS</code></td>
      <td>48</td>
    </tr>
    <tr>
      <td><code>MAX_VERTEX_UNIFORM_VECTORS</code></td>
      <td>256</td>
    </tr>
    <tr>
      <td><code>MAX_FRAGMENT_UNIFORM_VECTORS</code></td>
      <td>224</td>
    </tr>
    <tr>
      <td><code>MAX_VERTEX_ATTRIBS</code></td>
      <td>16</td>
    </tr>
    <tr>
      <td><code>MAX_VARYING_VECTORS</code></td>
      <td>15</td>
    </tr>
    <tr>
      <td><code>MAX_VIEWPORT_DIMS</code></td>
      <td>8192 x 8192</td>
    </tr>
  </tbody>
</table>
