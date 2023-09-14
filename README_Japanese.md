# slspec

### 要約

[slspec ファイル](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddy/UsersGuide#A--slspec:~:text=%2D%2D-,slspec,-Specifies%20a%20text) は、MRI のスライス/MB nのグループがどのように取得されたかを記載したファイルです。これは、[FSL の eddy --mporder オプション](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddy/UsersGuide#A--slspec:~:text=the%20next%20release.-,%2D%2Dmporder,-If%20one%20wants) を使ってボリューム内の体動を補正するのに必要です。詳しくはFSLのウェブサイトをご覧ください。

このjupyter-notebookは、dcm2nixを使ってdicom画像を変換したときにできるjsonファイルを使って、自動的にslspecテキストファイルを作成します。

マルチバンド1（マルチバンドなし）からマルチバンド8まで対応しています。GEとSiemensのマルチバンド1,2,4,8で動くことを確認していますが、うまく動作しない場合はIssueでご連絡ください。

### 必要なライブラリ

pandas

### 手順

1. 最初のセルのjsonファイル名'DWI.json'をご自分のjsonファイル名に置き換えてください。
2. 2.jsonファイルをこのノートブックと同じフォルダに置くか、パスを指定して下さい。
3. すべてのセルを実行すると、ノートブックのあるフォルダにslspecファイルが作成されます。

jsonファイルには'SliceTiming'が記載されている必要があります。記載がない場合は途中で処理を終了し、"Sorry, this json file doesn't have slice timing. Exitted and succeeding process was skipped"と表示されます。
