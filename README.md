# VRMVoicerWithChatGPT
VRMにしゃべってもらうことを体験するサンプルリポジトリです。

https://user-images.githubusercontent.com/1772636/229851106-14613be7-76a9-4217-979b-533e5df32237.mp4

# 処理概要
1. Unityを実行すると、音声入力待ちの状態になります。（上記動画では"塩の作り方を教えてください"といった後です）
2. 音声入力が完了すると、テキストで画面下に表示されます。（上記動画の"塩の作り方を教えてください"の箇所です）
3. 2に続いて、ChatGPTへテキストを基にリクエストを出してレスポンスを待ちます。（回答内容によって10秒ほどかかることがあります）
4. ChatGPTからレスポンスが返ってくると、その内容をVOICEVOXに連携して音声合成を待ちます。（
5. 音声合成が完了すると、VRMのBlendshapeとOVRLipSyncを利用してVRMのアバターがしゃべりだしてくれます。（上記動画はこの5からです）

# 前提
* Windows10（音声入力がWindows前提になっています）
* Unity 2021.2.4f1
* Oculus LipSync v29
* 動画の背景は有料Assetなのでこのリポジトリ含まれていません

# 使い方
1. OpenAIのAPIKeyを作成して、SampleSceneにいるTesterのInspectorのApi Keyに設定します
2. voicevox_engineをdockerで起動します。（dockerでなくても大丈夫です）
3. Unityを実行して、ConsoleにStart speech recognition, waiting for your voice...と出てきていることを確認します
4. 話しかけてください！

# VRMの入れ替え方
1. vrmをドラッグアンドロップでインポートします。
2. 1でインポートしたvrmをHierachyに配置します。
3. doreのPositionをコピーして、カメラ位置まで移動させます。
4. おそらく後ろを向いているのでY軸で180度回転させます。（doreのrotation参照）
5. doreを削除します。

## 注意
1. ときどき音声認識がうまく反応しないときがあります。その場合、再実行してみてください。

# OSS
[unity-voicevox-bridge](https://github.com/mikito/unity-voicevox-bridge) : MIT license
[voicevox_engine](https://github.com/VOICEVOX/voicevox_engine) : Unknown, LGPL-3.0 licenses found
[VRMLipSyncContextMorphTarget](https://github.com/TsubokuLab/VRMLipSyncContextMorphTarget)
[UniVRM](https://github.com/vrm-c/UniVRM) : MIT license
[UniTask](https://github.com/Cysharp/UniTask) : MIT license
