#プリセット

プロジェクト開発において、よくこのような状況が現れます。

1.審査時、美術では標準的なフォントの色、サイズを規定し、各UIに応用していましたが、ある日突然美術がデフォルトのフォントの色、店名、苦労しているUIの製作者がすべてのインターフェースを変更すると言ってしまい、大変なことになりました。**この場合は、デフォルトの属性設定やデフォルトの設定を使うと簡単に対処できます。1箇所だけ変更すれば、全体に影響が出ます。**

2.異なるインターフェースでは、ローカルに同じモジュールがあり、論理コードも同じである場合、**ページブロック+runtime（ページ論理クラス）を使うと簡単に対応できます。**

3.異なる界面では、局所的に同じ配置があり、一度修正したいと思います。複数の界面の同じ配置が一緒に変化します。**この場合はページネストやプリセットを使うと簡単に対応できます。**

上記のような需要に対して、LayaAirIDEは3つの案を提供しています。

**1.リソースのデフォルト属性の設定**（単一のコンポーネントに標準値を設定し、グローバル効果を変更します。）

**2.UIコンポーネントプロビジョニング**（ローカルUIレイアウトをプリセットとして保存し、別のページにドラッグして使用し、プリセット属性を変更し、グローバル効果が発生します。）

**3.ページネスト**（ローカルUIをページとして保存し、別のページにドラッグして多重化し、runtimeを加えて論理を多重化することもできる）

この三つのプリセットはどうやって使うかを紹介します。

###一.リソースのデフォルト属性の設定

1.リソースパネルでリソースを選択し、ダブルクリックしてリソース属性設定パネルを開きます。

![1](img\1.gif)（図1）

2.デフォルトのグローバルにコンポーネント属性値を設定し、例に示すように属性設定値を直接設定すればいいです。**注意：等号「=」の前後にスペースがないこと。**を選択します。図2に示すように、

![2](img\2.png)（図2）

表示効果は以下の通りです。

![3](img\3.png)（図3）

ある場所がプリセット情報を使用したくない場合は、直接に事前設定コンポーネントをUIページにドラッグして属性バーで対応する属性値を変更して、デフォルト値を上書きします。

**利点：コンポーネントに九宮の格とピクチャーのタイプを設けることができて、あるフォントの色を設定することができます。**

**短所：単一のコンポーネントのみを事前設定できます。カスタムグループの要素に属性値を設定できません。**



###二.UIコンポーネントプロビジョニング

1.ここではユーザー定義のBoxプリセットコンポーネントを作成し、ページの中でプリセットコンポーネントにする要素を使用する属性値を設定し、すべて選択してショートカットキーCtal+Bを押してBoxコンポーネントに結合します（開発者は自分のニーズに応じて対応するコンポーネントに変換できます）。図4に示すように、

![4](img\4.png)（図4）

2.階層ディレクトリから変換されたBoxコンポーネントをリソースリストにドラッグして、プリセットコンポーネントを生成します。図5に示すように、

![5](img\5.gif)</br/>(図5)

図5からは、カスタムコンポーネントがプリセットコンポーネントとして作成されると、リソースパネルに1つの.prefabは、拡張子としてのコンポーネントを生成し、UIインターフェースのBoxコンポーネントの色が変化することが分かる（この色は、コンポーネントをカスタムプリセットコンポーネントとして表す）。最後に異なるページでこのコンポーネントをドラッグして使用できます。

3.予め設定されたコンポーネントの属性値をあるインターフェースで変更したい場合は、UIインターフェース上でコンポーネントをダブルクリックして変更することができます。図6に示すように、

![6](img\6.png)（図6）

**利点：現在のページを直接ダブルクリックしてサブレベルのプロパティを変更できます。設定後もUI画面に表示されるのは依然としてコンポーネントです。**

**短所：既にセットされているコンポーネントの内部に新しい要素を追加できません。コンポーネント属性パネルの値を変更するしかありません。**



###三.ページネスト

プロジェクト開発では、UIページが複数のところで使用される機能がある場合があります。LayaAirIDEでは、直接UIページを他のUIページにドラッグして使用することができます。

図7、図8に示すように、

![7](img\7.png)（図7）

![8](img\8.gif)（図8）

図8では、作成されたUIページをそのままドラッグして別のUIページに配置します。これがUIページのネストです。

**優：任意にページに新しい要素を追加できます。**

**劣化：コンポーネントの属性は、あるページでは変更できません。ダブルクリックしてUIViewページに入るだけで変更できます。修正すると、使用するところは全部変わります。**



**結語:**

**3つのプリセットの共通の利点は、重複修正の操作を減らすことである。異なるインターフェースでプリセットコンポーネント（またはページ）を使ったら、直接にプリセットコンポーネント（またはページ）を変更すればいいです。使うところは変更されます。一つ一つ修正しなくてもいいです。**