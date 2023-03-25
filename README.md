# gishi-wajinden-countries

# 初めに
論文(仮)の補助データです。

対象論文
- 論文(仮)

# データ
CSVファイルの文字コードはUTF-8です。
## data/
- [gishi-wajinden-countries-pub.xlsx](data/gishi-wajinden-countries-pub.xlsx)
  - 全てのCSVファイルをまとめたものです。詳細は各CSVファイルの説明をご覧ください。
  - 元はGoogle Spreadsheetで編集し、Excel形式に変換しました。
- [gishi-wajinden-countries-pub - DB.csv](data/gishi-wajinden-countries-pub%20-%20DB.csv)
  - 使用している電子辞書や地名データベースの一覧です。
- [gishi-wajinden-countries-pub - 参考文献.csv](data/gishi-wajinden-countries-pub%20-%20%E5%8F%82%E8%80%83%E6%96%87%E7%8C%AE.csv)
  - 参考文献です。
- [gishi-wajinden-countries-pub - 記号.csv](data/gishi-wajinden-countries-pub%20-%20%E8%A8%98%E5%8F%B7.csv)
  - 発音表記で独自に定義している記号の一覧です。
- [gishi-wajinden-countries-pub - 発音-国名.csv](data/gishi-wajinden-countries-pub%20-%20%E7%99%BA%E9%9F%B3-%E5%9B%BD%E5%90%8D.csv)
  - 国ごとの漢字の発音データ。他にも発音パターンはあり得ますが、候補として検討した物のみ記載。記号の詳細は pronounciation-single-char.csv を参照。
- [gishi-wajinden-countries-pub - 発音-単漢字.csv](data/gishi-wajinden-countries-pub%20-%20%E7%99%BA%E9%9F%B3-%E5%8D%98%E6%BC%A2%E5%AD%97.csv)
  - 個別の漢字の発音データ。後漢および魏晋期の発音を辞書を基に補完・修正して記載しています。単純なテーブルではなく、1つの漢字は6行分使用し、その中で細分項目が縦にも並んでいます。参考文献やツールは上記参照。
  - 「項目」「値」列
    - 「小學堂字號」電子辞書で使われる文字コード。一つの漢字に複数の音がある場合はこれにより区別されます。[小學堂]
    - 「Pinyin」現代語の発音。[小學堂]
    - 「声調(廣韻)」中古音の声調。[小學堂]
    - 「等(廣韻)」中古音の等(division, grade)。3bは重紐3等 (chongniu, doublets)。 [小學堂]
    - 「Definition」」意味。一つの漢字に複数の音がある場合はこれにより区別されます。
  - 「時期」「韻部・韻目」「辞書音」列。辞書掲載の韻および再構音(擬音)の情報です。#は未掲載の部分です。
  - 「推定音」列: 後漢、魏晋の音について筆者が補完・修正を行ったものです。補完・修正部分はカッコ()がついています。
  - 「日琉祖語」「上代日本語」列: 推定音に対して半機械的に日本語の読みに変換したものです。複数の発音が対応しえます。厳密には前後の音節や語中の位置にも影響されます。{X}は音節省略の可能性で省略部分はXを含む、`は清音・濁音の両方の可能性がある、X1, X2は上代特殊仮名遣いの甲乙です。
  - 「補完・修正コメント」列: I (Initial)頭子音、M (Medial)介音、R (Rhyme)韻、C (Coda)韻尾、について補完・修正理由を説明しています。
  -	「その他のコメント」列
- [gishi-wajinden-countries-pub - 候補検討.csv](data/gishi-wajinden-countries-pub%20-%20%E5%80%99%E8%A3%9C%E6%A4%9C%E8%A8%8E.csv)
  - 第1候補(比定地)のリスト。地図上でマーカーをプロットするのに使用しています。上の方に固めてあります。
  - 第2候補以下も含めた候補地名のスコアリング。下の方に固めてあります。
  - 「TYPE」列: 第1候補のみ設定。女王国=女王に属する国の意味。女王国H=既存説有力、女王国M=同じ比定の既存説あり、女王国L=同じ比定の既存説なし、その他H=既存説有力、その他M=同じ比定の既存説あり。
- [gishi-wajinden-countries-pub - 既存研究.csv](data/gishi-wajinden-countries-pub%20-%20%E6%97%A2%E5%AD%98%E7%A0%94%E7%A9%B6.csv)
  - 先行研究による遠絶二十一国の比定地リスト。文献は上記参照。
  - 先行研究として主に発音に頼って遠絶二十一国の部分の比定を行っているものを選んでいます。
  - e のセルは文献中に記載がなく既存説[石原1951]をそのまま踏襲しているとみられるところ。
- [gishi-wajinden-countries-pub - 編集-出土遺跡別-辻田I.csv](data/gishi-wajinden-countries-pub%20-%20%E7%B7%A8%E9%9B%86-%E5%87%BA%E5%9C%9F%E9%81%BA%E8%B7%A1%E5%88%A5-%E8%BE%BB%E7%94%B0I.csv)
  - 三角縁神獣鏡「舶載I」段階出土古墳の築造年代リスト。出土古墳が明確な鏡の出土古墳のリストです。三角縁神獣鏡出土古墳のリストは[下垣2010]付録、三角縁神獣鏡の編年は[辻田2007]に依っています。古墳ごとの枚数・鏡種は無視しています。地図上でマーカーをプロットするのに使用しています。
  - 「status_code」列: 0=前期前半、1=前期(前後半不明)、2=前期後半以降、3=不明。10番以降は出土古墳が伝承・推測である事を表し10を引いた値の定義は同じ。
  - 「古墳特定」列: 鏡が出土した古墳が特定できるか。古墳群レベルでの特定ないし発見時状況が不明な場合などは0。
  - 「集成編年」列: 集成編年(10期編年)による古墳の築造年代。
  - 「時期」列: 鏡が出土した古墳の築造時期。前期前半/前期後半/中期/後期の粒度です。
  - 「コメント」列: 古墳の築造年代の判定根拠。
  - 「文献」列: 古墳の築造年代は[奈良女]の前方後円墳データベースに記載の場合はそれで、未記載の場合は個別に「文献」列に記載の参考文献を参照しています。
- [gishi-wajinden-countries-pub - 編集-出土遺跡別-伝辻田I.csv](data/gishi-wajinden-countries-pub%20-%20%E7%B7%A8%E9%9B%86-%E5%87%BA%E5%9C%9F%E9%81%BA%E8%B7%A1%E5%88%A5-%E4%BC%9D%E8%BE%BB%E7%94%B0I.csv)
  - 三角縁神獣鏡「舶載I」段階出土古墳の築造年代リスト。出土古墳が伝承・推測である鏡の出土古墳のリストです。詳細は上記参照。

# 参考文献
参考文献の表をご覧ください。
- [gishi-wajinden-countries-pub - 参考文献.csv](data/gishi-wajinden-countries-pub%20-%20%E5%8F%82%E8%80%83%E6%96%87%E7%8C%AE.csv)



# ライセンス

- This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>. (CC-BY 4.0)
- <a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>

# お問い合わせ
- ryokawameister
- at
- gmail.com

