# gishi-wajinden-countries

# 初めに
論文(仮)のサポートサイトです。使用されているデータを公開しています。

対象論文
- 論文(仮)

# データ
CSVファイルの文字コードはUTF-8です。
## data/
- [gishi-wajinden-countries-pub.xlsx](data/gishi-wajinden-countries-pub.xlsx)
  - 全てのCSVファイルをまとめたものです。詳細は各CSVファイルの説明をご覧ください。
  - 元はGoogle Spreadsheetで編集し、Excel形式に変換しました。
- [location-score.csv](data/location-score.csv) : 発音-単漢字
  - 第1候補(比定地)のリスト。地図上でマーカーをプロットするのに使用しています。上の方に固めてあります。
  - 第2候補以下も含めた候補地名のスコアリング。下の方に固めてあります。
  - 「TYPE」列: 第1候補のみ設定。女王国=女王に属する国の意味。女王国H=既存説有力、女王国M=同じ比定の既存説あり、女王国L=同じ比定の既存説なし、その他H=既存説有力、その他M=同じ比定の既存説あり。
- [mirrors-tsujita-h1-ok.csv](data/mirrors-tsujita-h1-ok.csv) : 編集-出土遺跡別-辻田I
  - 三角縁神獣鏡「舶載I」段階出土古墳の築造年代リスト。出土古墳が明確な鏡の出土古墳のリストです。三角縁神獣鏡出土古墳のリストは[下垣2010]付録、三角縁神獣鏡の編年は[辻田2007]に依っています。古墳ごとの枚数・鏡種は無視しています。地図上でマーカーをプロットするのに使用しています。
  - 「status_code」列: 0=前期前半、1=前期(前後半不明)、2=前期後半以降、3=不明。10番以降は出土古墳が伝承・推測である事を表し10を引いた値の定義は同じ。
  - 「古墳特定」列: 鏡が出土した古墳が特定できるか。古墳群レベルでの特定ないし発見時状況が不明な場合などは0。
  - 「集成編年」列: 集成編年(10期編年)による古墳の築造年代。
  - 「時期」列: 鏡が出土した古墳の築造時期。前期前半/前期後半/中期/後期の粒度です。
  - 「コメント」列: 古墳の築造年代の判定根拠。
  - 「文献」列: 古墳の築造年代は[奈良女]の前方後円墳データベースに記載の場合はそれで、未記載の場合は個別に「文献」列に記載の参考文献を参照しています。
- [mirrors-tsujita-h1-den.csv](data/mirrors-tsujita-h1-den.csv) : 編集-出土遺跡別-伝辻田I
  - 三角縁神獣鏡「舶載I」段階出土古墳の築造年代リスト。出土古墳が伝承・推測である鏡の出土古墳のリストです。詳細は上記参照。
- [phonation-country.csv](data/phonation-country.csv) : 発音-国名
  - 国ごとの漢字の発音データ。他にも発音パターンはあり得ますが、候補として検討した物のみ記載。記号の詳細は pronounciation-single-char.csv を参照。
- [phonation-single-char.csv](data/phonation-single-char.csv) : 発音-単漢字
  - 個別の漢字の発音データ。後漢および魏晋期の発音を辞書を基に補完・修正して記載しています。単純なテーブルではなく、1つの漢字は6行分使用し、その中で細分項目が縦にも並んでいます。参考文献やツールは下記[辞書](#辞書)を参照。
  - 「項目」「値」列
    - 「小學堂字號」電子辞書で使われる文字コード。一つの漢字に複数の音がある場合はこれにより区別されます。[小學堂]
    - 「Pinyin」現代語の発音。[小學堂]
    - 「声調(廣韻)」中古音の声調。[小學堂]
    - 「等(廣韻)」中古音の等(division, grade)。3bは重紐3等 (chongniu, doublets)。 [小學堂]
    - 「Definition」」意味。一つの漢字に複数の音がある場合はこれにより区別されます。
  - 「時期」「韻部・韻目」「辞書音」列。辞書掲載の韻および再構音(擬音)の情報です。#は未掲載の部分です。
    - 上古音(先秦BS) 韻部・辞書音 [Baxter2014] (電子データ[Baxter2014b])
    - 上古音(先秦Z) 韻部・辞書音 [鄭張尚芳2003] (電子辞書[Wiktionary])
    - 上古音(後漢) 韻部[羅常培1958] (電子辞書[小學堂])、辞書音[Schuessler2007]
    - 中古音(魏晋) 韻部・辞書音 [丁邦新1975] (電子辞書[小學堂]) 
    - 中古音(ONW) 辞書音 [Coblin1994]
    - 中古音(隋唐) 韻目『廣韻』(電子辞書[小學堂])、辞書音 [鄭張尚芳2003] (電子辞書[Wiktionary])
  - 「推定音」列: 後漢、魏晋の音について筆者が補完・修正を行ったものです。補完・修正部分はカッコ()がついています。
  - 「日琉祖語」「上代日本語」列: 推定音に対して半機械的に日本語の読みに変換したものです。複数の発音が対応しえます。厳密には前後の音節や語中の位置にも影響されます。{X}は音節省略の可能性で省略部分はXを含む、`は清音・濁音の両方の可能性がある、X1, X2は上代特殊仮名遣いの甲乙です。
  - 「補完・修正コメント」列: I (Initial)頭子音、M (Medial)介音、R (Rhyme)韻、C (Coda)韻尾、について補完・修正理由を説明しています。
  -	「その他のコメント」列
- [related-work.csv](data/related-work.csv) : 既存研究
  - 先行研究による遠絶二十一国の比定地リスト。文献は下記[先行研究](#先行研究)参照。
  - 先行研究として主に発音に頼って遠絶二十一国の部分の比定を行っているものを選んでいます。
  - e のセルは文献中に記載がなく既存説[石原1951]をそのまま踏襲しているとみられるところ。


# 参考文献
## 先行研究
- [新井1716] 新井白石 (1716?)。『古史通或問』下巻。
- [内藤1910] 内藤虎次郎 (1910)「卑弥呼考」、『芸文』1(2), p59-73. 1(3), p87-10. 1(4), p45-67.
- [山田1922] 山田孝雄 (1922). 「狗奴国考」、『考古学雑誌』, 12(8)(271), p.447-459. 12(9)(272), p.515-528. 12(10)(273), p.610-621. 12(11)(274), p.692-697. 12(12)(275), p.735-744. 日本考古学会.
- [井上1951] 井上光貞 (一九五一)。「國造制の成立」史學雑誌六〇―一一。
- 米倉二郎 (1953) 「魏志倭人伝に見ゆる斯馬国以下の比定」、『史学研究』 Vol.52, p.16-22, 1953.
- [牧1968] 牧健二(1968)。「女王国及びその属領の領域並びに倭の三十国の所在地の考定」『日本の原始国家』、9章、p.345-382。有斐閣。
- [田中1985] 田中卓(1985)。「邪馬台国と稲荷山刀銘」、『田中卓著作集3』、国書刊行会。
- [長田2010] 長田夏樹 (2010)。「『倭人伝』の訓み方」、『新稿 邪馬台国の言語』第1章、p.12-99。学生社。(第1版1979)
- [安本2003九] 安本美典 (2003)。『推理◎古代日本語の謎 「倭人語」の解読』、勉誠出版。
- [安本2003畿] (同上)
-	[Bentley2008] John R. Bentley. (2008). "The Search for the Language of Yamatai." Japanese Language and Literature Vol. 42, No. 1, p. 1-43
- [大⽵2013] 大⽵昌⺒ (2013)。「「魏志倭人伝」の漢字音写からみた３世紀日本語のハ行子音の音価」, 京都大学文学研究科セミナー資料。
(https://www.academia.edu/27524411/The_phonetic_value_of_the_consonant_p_in_third_century_Japanese_An_approach_using_Chinese_transcriptions_in_the_Gi%C5%A1i_Wa%C7%B0inden_%E9%AD%8F%E5%BF%97%E5%80%AD%E4%BA%BA%E4%BC%9D_%E3%81%AE%E6%BC%A2%E5%AD%97%E9%9F%B3%E5%86%99%E3%81%8B%E3%82%89%E3%81%BF%E3%81%9F3%E4%B8%96%E7%B4%80%E6%97%A5%E6%9C%AC%E8%AA%9E%E3%81%AE%E3%83%8F%E8%A1%8C%E5%AD%90%E9%9F%B3%E3%81%AE%E9%9F%B3%E4%BE%A1)
- [すきえんてぃあ2021] すきえんてぃあ (2021)。「言語学の勝利〜〜！「魏志倭人伝」完全解読！3世紀当時の発音から地名や方言とも照らし合わせた研究がすごい 邪馬台国の場所も推定される - Togetter」、 https://togetter.com/li/1648850
- [鬼塚2021] 鬼塚健太郎 (2021)。「#魏志倭人伝 #完全解読 その1 国名比定」 https://www.awexion.jp/cgi-bin/a.cgi/.P1880000000000004188000000000000F/Cover/Index



## 辞書
- [Schuessler2007] Axel Schuessler. (2007). "ABC Etymological Dictionary of Old Chinese." University of Hawaii Press. (電子版 Google Books)
- [Baxter2014a] William H. Baxter and Laurent Sagart. (2014). "Old Chinese: a new reconstruction. " New York: Oxford University Press.
- [鄭張尚芳2003] 鄭張尚芳 (二〇〇三)。『上古音系』。上海教育出版社。
- [羅常培1958] 羅常培、周祖謨 (一九五八)。『漢魏晉南北朝韻部演變研究』。科學出版社。
- [丁邦新1975] 丁邦新 (一九七五)。『魏晉音韻研究』。中央研究院歷史語言研究所專刊之六十五。
- [Baxter2014b] William H. Baxter and Laurent Sagart. (2014). Downloads. https://ocbaxtersagart.lsait.lsa.umich.edu/ .
- [Coblin1994] W. Sowth Coblin (1994). "A compendium of phonetics in Northwest Chinese." JCL Monograph 7. [Schuessler2007]に再録。
- [Wiktionary] Wiktionary, the free dictionary.  https://en.wiktionary.org/wiki/Wiktionary:Main_Page .
- [小學堂] 小學堂「漢字古今音資料庫」 https://xiaoxue.iis.sinica.edu.tw/ .

## その他の文献
- [辻田2007] 辻田淳一郎 (2007) 『鏡と初期ヤマト政権』すいれん舎
- [下垣2010] 下垣仁志 (2010). 『三角縁神獣鏡研究事典』 吉川弘文館. ISBN 978-4-642-01454-0。
- [奈良女] 奈良女子大学 古代学学術研究センター。「解説 |前方後円墳データベース」 https://zenkoku-kofun.nara-hgis.jp/zenkoku_kofun_home.html
- [石原1951] 石原道博(編訳)「新訂 魏志倭人伝・後漢書倭伝・宋書倭国伝・隋書倭国伝-中国正史日本伝(1)」岩波文庫 (1951)
- [広瀬1991] 広瀬和雄 (1991). 「前方後円墳の畿内編年」 in 近藤義郎 (編)「前方後円墳集成〈中国・四国編〉」山川出版社.


# ライセンス

- This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>. (CC-BY 4.0)
- <a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a>

# お問い合わせ
- ryokawameister
- at
- gmail.com

