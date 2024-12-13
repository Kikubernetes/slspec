# slspec

### 概要  
このリポジトリでは、FSLの`eddy --mporder`オプションを使用してMRIデータの体動補正に必要な`slspec`ファイルを自動生成するツールを提供しています。`slspec`ファイルは、スキャン時にスライスまたはマルチバンド（MB）グループがどのように取得されたかを定義します。詳細については、[FSLのドキュメント](https://fsl.fmrib.ox.ac.uk/fsl/docs/#/diffusion/eddy/users_guide/index?id=-jsonfilename-or-slspecfilename)をご参照ください。

（最近のFSLバージョンを使用している場合は、`--json`オプションを使用してJSONファイルを直接利用することもできます。詳しくは上記のドキュメントをご覧ください。）

---

### 特徴  
このJupyter Notebookは、`dcm2niix`がDICOMからNIfTIに変換する際に生成するJSONファイルから`slspec`テキストファイルを作成します。

- マルチバンドMB1（マルチバンドなし）からMB8（マルチバンド8）までの取得をサポートしています。
- GEおよびSiemensのMB1、MB2、MB4、MB8のデータセットでテスト済みです。
- うまくいかない場合はissueでフィードバックをお願いします。

---

### 必要なライブラリ  
Pythonライブラリ：`pandas`

---

### 使用方法  

1. このリポジトリをクローンするか、ノートブック「slspec-multiband.ipynb」をダウンロードしてください。Google Colabで開く場合は、「Open in Colab」ボタンをクリックしてください。  
1. ノートブックの2番目のセルで、`DWI.json`を使用するJSONファイルの名前に置き換えてください。  
(JSONファイルをノートブックと同じディレクトリに配置するか、パスを指定してください。)   
1. すべてのセルを実行すると、ノートブックが配置されているフォルダに`slspec`ファイルが作成されます。

**注意**：JSONファイルには`SliceTiming`フィールドが含まれている必要があります。

