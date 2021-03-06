## Course structure
https://docs.google.com/presentation/d/1-jkoseBpWyCS-Kepw_uJi3tV_EGZj0QEZ_mFRSqnFbw/edit#slide=id.g484b925ea_01
### The perfect data science experience
(versus real life)

#### Attributes
- Clearly defined hypotheses of interest, specified a priori
- Experimental design available
   - Randomization used across a treatment of interest
   - Stratification on nuisance variables
- Random sample from a population of interest
- Data directly able to interrogate hypotheses
- Dataset creation/merging goes smoothly
- No missing data or dropout
- Analysis is robust without need for advanced modeling
- Conclusions are clear
   - Parsimonious knowledge gained via the experiment
- Decision is obvious given the data

#### Attributes of data science in real life
- Data is needed to inform hypotheses and interrogate them
- Multiple comparisons are an issue
- Experimental design options are limited. Or, data is observational
   - Randomization is not available
   - Data is retrospective
- The population being studied isn’t the population of interest
- The data don’t have the exact measurements that you need to evaluate the hypotheses
- Dataset is problematic
   - Merging is problematic with multiple matches, no matches
   - Data entry errors
- Missing data
- Advanced modeling is required, similarly advanced computing needed to fit the model, issues with robustness and bugs
- Conclusions are indeterminant
- Decision is not substantially further informed by the data

---
### 完璧なデータサイエンスエクスペリエンス（実生活に対して）

#### 属性
- 明確に定義された興味のある仮説、アプリオリに指定
- 実験デザインが利用可能
   - 関心のある治療全体で使用されるランダム化
   - 迷惑変数の層別化
- 関心のある母集団からのランダムサンプル
- 仮説を直接調査できるデータ
- データセットの作成/マージがスムーズに進みます
- 欠落データやドロップアウトはありません
- 高度なモデリングを必要とせずに分析が堅牢
- 結論は明確です
   - 実験を通じて得られたPar約的な知​​識
- データがあれば決定は明らか

### 実生活におけるデータサイエンスの属性
- 仮説を伝え、それらを調査するためにデータが必要です
- 多重比較は問題です
- 実験的な設計オプションは限られています。または、データは観測的です
   - ランダム化は利用できません
   - データは遡及的
- 調査対象の人口は関心のある人口ではありません
- データには、仮説を評価するために必要な正確な測定値がありません
- データセットに問題がある
   - 一致は複数の一致で問題があり、一致しない
   - データ入力エラー
- 欠落データ
- 高度なモデリングが必要であり、モデルに適合するために同様に高度なコンピューティングが必要、堅牢性とバグの問題
- 結論は不確定です
- データによって決定が実質的にさらに通知されることはありません


### 1. The data pull is clean
#### Lecture slides 
https://docs.google.com/presentation/d/106TF1VtIrS3Ze09_9kgPZY14vPrc9wlMNg9E5XWVDo4/edit?usp=sharing

1. **サマリーテーブルの構築**。サマリーテーブルは、データエラーをキャッチするのに非常に役立ちます。
特に便利なのは、単位を追跡し、いくつかの要約（平均、中央値、最大値、最小値、その他の変位値および標準偏差）を記録することです。
時間の経過に伴うレポートを比較することで、処理中にあるべきではないことが変化しているかどうかを確認できます。
2. **回帰診断**。回帰分析は、データ分析における普遍的な最初のステップです。
回帰診断は、分析に現れるデータ品質エラーをキャッチするのに役立ちます。
いくつかの有用な回帰診断は次のとおりです： **残差** -応答と適合値の差、**ハット対角線**、
これらは予測子の空間内でデータ行がどの程度変動するかを考慮し、
**DF適合**、**DFベータ**、**クック距離**これらは適合値をどれだけ考慮するか点が近似に含まれない場合、係数は変化しますか？
残差を押して残差を残します-分析からポイントが残されたときに予測がどれだけ変化しますか

### 2. The experiment is carefully designed, designed
https://docs.google.com/presentation/d/16CTB8spdjaz3xy4PZ7cvB4f28XKNduvANuesITypvbU/edit?usp=sharing
https://docs.google.com/presentation/d/1DqxwVDvV5JRdzlGdEB9FKcK2UnZ9j1YANlgxwVbCbV8/edit?usp=sharing

重要なトピックは**交絡(confounding)** です。交絡は、2つのことを比較したいときに発生し、3番目が邪魔になります。例として、広告のパフォーマンスと購入を調べたいとします。ただし、広告は異なるサイトで実行されたため、異なる視聴者に表示されました。オーディエンスによって購入パターンが異なる場合があるため、表示される違いは広告キャンペーンによるものではなく、オーディエンスによるものである可能性があります。交絡の詳細はこちらhttps://en.wikipedia.org/wiki/Confounding

実験におけるランダム化の興味深い要素は、**因果関係(causal)** を推定する能力です効果。因果効果は、特定の治療で観察された被験者の結果から、対照として観察された結果を引いた差として定義されます。ただし、被験者は治療レベルの1つしか受けられないため、これら2つのうち1つだけが観察されます。もう1つは反事実と呼ばれます。このため、反事実的な影響を推定できます。ただし、ランダム化がある場合、仮定の下で、平均化された反事実的影響を推定することができます。データを使用して因果効果を推定する方法の研究は、因果推論と呼ばれます。因果推論と反事実の最も有用な側面は、それらについて考えることが、さまざまな実験計画について考えるのに役立つということです。因果推論の詳細については、こちらをご覧くださいhttps://en.wikipedia.org/wiki/Rubin_causal_model

### 3. The experiment is carefully designed, things to do

A/B Testing https://docs.google.com/presentation/d/1sdFDud2Wrv8PmmY2_XDknkg1tgvpheNMD_9Old9IA8c/edit?usp=sharing

Bias & Sampling https://docs.google.com/presentation/d/133bBtOQHPaBYSu7RBmbGuu8PN0UUxt278qTqOWSuJIQ/edit?usp=sharing

Adjustment / blocking https://docs.google.com/presentation/d/1xDY7Qh_ip4HA01unq8mxLF7M0ti8AGA0xmKeOihkqjg/edit?usp=sharing

交絡に対処する1つの方法は、設計の段階です。サイト間で広告キャンペーンをランダム化すると、（少なくとも高い確率で）オーディエンスは同様になります。もちろん、運が悪くなる可能性があり、視聴者の不均衡が依然として発生する可能性がありますが、より多くのサイトにわたってランダム化するにつれて、その可能性は小さくなります。これは、**A/B**テストの前提です。A/Bテストでは、比較対象グループ（A対B）を可能な限り比較可能にするために、ランダム化を使用した実験を正式に設計します。A/Bテストの詳細については、こちらをご覧ください（専門用語ではありません）：https://en.wikipedia.org/wiki/A/B_testing

ランダム化がない場合、何ができますか？また、明らかに交絡因子となる変数を知って収集する場合、治療グループ間のバランスを偶然に残すのではなく、それを設計に組み込むべきではありませんか？これらの質問は、ブロックと調整によって対処されます。で**ブロックされた実験**では、我々は潜在的な交絡変数のレベル内ランダム化します。**調整(Ajustment)** データが収集された後に使用される戦略です。調整では、交絡変数のレベルを固定した状態で、予測変数と結果の関係を調べます。したがって、視聴者の人口統計が広告キャンペーンと購入の関係を混乱させる場合、人口統計内の関係に注目します。回帰モデルは、いくつかの仮定を使用して、この種の調整を自動的に行います。変数を回帰モデルに入れると、関心のある関係にあらゆる種類の影響を与える可能性があります。講義ではいくつかの例を検討します。ブロックの詳細についてはこちらをご覧くださいhttps://en.wikipedia.org/wiki/Blocking_(statistics）および回帰調整はこちらhttp://oem.bmj.com/content/62/7/500.full

実験計画の最後の側面は**サンプリング**です。理想的には、ランダムサンプリングを使用して、高い確率で、記述したい母集団の適切な表現であるサンプルを取得できます。ただし、多くの場合、実験のサンプリングプロセスを制御することは不可能です。**サンプリングバイアス**は、サンプルがターゲット母集団を示していない場合に発生し、推論がオフになります。サンプルの問題を回避するための3つの戦略について説明します。まず、(1)ランダムサンプリングです。2つ目は、(2)特定の観測がモデルにより多くの影響を与えることができるようにするプロセスである重み付けです。(3)最後はモデリングです。つまり、サンプルにバイアスをかけているプロセスをモデル化しようとしています。サンプリングバイアスの詳細については、こちらをご覧くださいhttps://en.wikipedia.org/wiki/Sampling_bias

### 4. Results of analyses are clear

Multiple comparisons: https://docs.google.com/presentation/d/1TcDBpbMHh1dmL9Jwq_51S6U-PyMy-jkBjJGPMsaZrCQ/edit?usp=sharing

Effect size: https://docs.google.com/presentation/d/1alJNwPcJLUBwLnMsrF1bmSIaqm_MCDpq0nYX-L5NHS4/edit?usp=sharing

Comparing to known effects: https://docs.google.com/presentation/d/1ubNBV_EXiHvv-TP3iY4qYaxiPbjFtz2rqu5HkVbTGuQ/edit?usp=sharing

Negative controls : https://docs.google.com/presentation/d/1-TgW9W_lazs9Jx6mZM0CYQBoJWzxU2-8wJOqvgRqbsA/edit?usp=sharing

さらに議論する前に、**仮説検定**の基本的な理解があることを確認する必要があります。仮説検定では、統計を使用して2つの仮説を決定します。1つをデフォルトの仮説（帰無仮説）として設定し、もう1つを代替仮説として設定します。帰無仮説を棄却して代替案を結論付けることを困難にします（多くの証拠が必要です）。これは、nullを拒否し、誤って代替を結論付ける可能性を低く設定することで行われます（通常5％）。多くの場合、仮説検定の結果は**p値**で要約されます。小さなp値（0に近い）は代替をサポートし、大きな値（1に近い）はnullをサポートします。誤ってnullを5％で拒否する確率を制御する場合、p値が0.05未満の場合はnullを拒否します。

仮説検定の結果を**効果**と混同しないでください。したがって、2つのグループ間の平均が異なるかどうかをテストする場合、仮説検定の結果はp値または検定の結論になり、効果は平均間の差になります。**信頼区間(confidence interval)** は、不確実性を組み込んで効果の推定値です。

この講義では、分析結果が明確でない方法と、それと戦ういくつかの方法について説明します。

まず、**複数の比較**について説明します。多くのモデルの適合から、または多くの事柄に関心があるために、多くの仮説検定を実行すると、実際には有意ではないにせよ単に偶然に有意な結果が見られる可能性が高くなります。このxkcdコミックストリップは、これについて素晴らしいhttps://xkcd.com/882/ を説明しています。この講義では、多重比較と戦うための1つのソリューション、Bonferroni補正を紹介します。ここでは、p値に実行したテストの数を掛けてから、p値を検討します。これは管理者にとって最も便利な多重比較ルールです。オンザフライで簡単に実行でき、レポートの議論中に実行できるためです。

次に、効果またはその大きさの重要性をどのように解釈するかを実際に知らないという問題を考えます。この場合、適切な戦略は、既知の効果を持つ他の変数と比較することです。私たちは、ハードボリュームの例である、脳の体積損失に対する鉛暴露を考えます。ここでは、この効果の大きさを、脳ボリュームの低下に対する加齢の大きさと比較しました。それから、「鉛の効果は月齢1/2の増加に似ている」というような声明を出すことができます。

最後に、かなり複雑な処理および分析ストリームが実行された設定を検討します。多くの場合、このような設定では、観察される効果が本物であるか、プロセスのアーティファクトであるかが懸念されます。繰り返しますが、比較のために脳画像の例を使用しました。人々はしばしば、脳のイメージングの効果は偽物であると信じています。そのため、多くの場合、人々は脳室（脳の問題がなく、脳脊髄液のみが存在する脳の領域）で分析を実行します。これは、**ネガティブコントロール**の実行と呼ばれます。それ以外の点では、良好なネガティブコントロールは実際の研究と同様です。たとえば、脳室は脳の真ん中にあり、他の脳領域のすべての処理の対象となるため、脳イメージングの例で機能します。対照的に、分析を通じて肘の画像を実行することはそれほど魅力的ではありません。ネガティブコントロールの詳細については、http：//study.com/academy/lesson/negative-control-definition-experiment-quiz.html をご覧ください。


### 5. The decision is obvious

The decision is (not) obvious: https://docs.google.com/presentation/d/1o-WUGyT74xgY4iRP_G1Z89VB7znMh15fUsfLrR_vrf4/edit?usp=sharing

Estimation target is relevant: https://docs.google.com/presentation/d/1tzGlR42QSvxw5OqlOdreBBoqGW1pguUsnhFb_SjH8FE/edit?usp=sharing

理想的には、分析が完了したら、データから決定するのは明らかです。ここでは、決定が明らかではない2つの一般的な事例について説明します。

まず、結果が曖昧な場合を考えます。たとえば、p値は0.05前後であり、5％のエラー率が標準です。次に、決定が明確であっても結果を測定できないため、代理変数で分析が実行された場合を考えます。

決定を下すためのデータの信頼性に関するこれらの懸念は、未測定の交絡因子、サンプリングバイアス、クラウドに重大なまたは重要でない発見を引き起こした可能性のある他のフォームバイアスなど、すでに対処された他のすべての懸念に加えてあります。ただし、以前の講義では、これらの問題に対するいくつかの救済策を提供したため、上記の最初の2つの懸念事項に限定しましょう。

統計的発見の重要性におけるサンプルサイズの役割について普遍的なコンセンサスがないことに注意することは興味深いです。わずかに重要な調査結果は、大きなサンプルサイズから信頼性を獲得しますか、それとも、仮説を調査するためにこれだけのデータでより明確にすべきだったので、それは苦しみますか？リチャード・ロワイヤルは、このアイデアについて「有意性検定の意味に対するサンプルサイズの影響」という魅力的な論文を書きました。これはやや挑戦的な論文ですが、読みたければ仮説検定の奇妙な癖をうまくカバーしています。

サンプルサイズに関する説明の1つは明確です。結果がnullで、サンプルサイズが非常に小さかった場合、nullの結果は驚くことではありません。これは、研究が成功するように設定されていなかったためです。これが**力**の考え方です。パワーは、偽の場合に帰無仮説を棄却する確率です。もっとパワーが欲しい。低出力の研究は、ばらつきがあるという理由だけで、nullが真であるかどうかに関係なく拒否することはないでしょう。電力は、サンプルサイズを介して実験の設計時に制御されます。ただし、実験が実行された後は、電力について行うことはあまりありません。多くの場合、実験が行われた後、検出力の欠如または真の非有意性による非有意な結果を区別しようとするために、計算力のアイデアが得られます。これは悪い考えです（この原稿http://amstat.tandfonline.com/doi/abs/10.1198/000313001300339897 を参照）。ただし、新しい調査を実施したり、既存の調査のデータを取得したりする可能性があります。

私たちが検討する2番目の問題は、望ましい結果が測定可能ではないが、いくつかの代替が測定可能なものです。これは非常に一般的です。たとえば、体脂肪率のBMI、経済的健康のGDP、実際のカロリー消費の代わりの食物摂取頻度アンケートなど。サロゲートの使用は、結果または予測子、あるいはその両方に対して発生する可能性があります。サロゲート変数が予測子として使用される場合、**測定誤差**のフィールドにはいくつかのツールがあります（この素晴らしい本http://www.amazon.com/Measurement-Error-Nonlinear-Models-Perspective/dp/1584886331 を参照）。特に便利なものは**SimEx**と呼ばれます。結果として、問題は**代理結果**と呼ばれます（これらの素晴らしいメモを参照してくださいhttp://depts.washington.edu/ssbiost/PRESENTATIONS/DeMets.pdf ）理想的には、代理人が真の結果に偏りがなく、分散を知っていることがわかります。これは、ゴールドスタンダードの研究を行うことができる場合に発生する可能性があります。あなたがそれを知らない場合、2番目の最良のケースは、それを推定するためのデータを持つことです。たとえば、BMIの例では、サンプルのサブセットで体脂肪率とBMIを測定できます。

代理を評価するためのキャリブレーションデータがない場合、仮定または**感度分析**によるモデリングのいずれかになります。

最後に、代理変数が実際の結果の推定値のように信頼できない場合、研究をまったく行わない方が良いという結論に達する必要があります。


### 6. The analysis product is awesome


Lecture notes:

Reproducibility: https://docs.google.com/presentation/d/1hrzer7bpGn8jzN9QlPEfgq3LhiVh25XEmiJuCYOedNk/edit?usp=sharing

Version control: https://docs.google.com/presentation/d/1jfLVMX-OK8u4T4pzT5mT4pJ75g3yhng1G-rS40Md1sM/edit?usp=sharing

この講義では、分析の結果について考察します。これは通常、何らかのレポートまたはプレゼンテーションです。分析が十分に進んでいる場合、アプリまたはWebページである可能性があります。データ製品の技術開発のトピックに関するコースクラスがありますhttps://www.coursera.org/course/devdataprod

製品がレポートである場合、理想的には、明確で簡潔に書かれており、素晴らしい物語と興味深い結果が得られます。ただし、データサイエンスマネージャーのニーズは十分に変化するため、すべての設定で遍在する優れた最終製品を生み出す2つのコンポーネントに焦点を当てています。これらは、**レポートを再現可能**にし、レポートとコードの**バージョンを管理**しています。

再現性のある分析では、他の人はもちろんのこと、自分の分析を再現するように人々に依頼すると、しばしば異なる結果が得られることもあります。再現可能なレポートを作成するコースクラスがありますhttps://www.coursera.org/course/repdata再現可能なレポートに適切なツールを使用する利点は多数あります。再現性の目標の達成を劇的に支援するだけでなく、コードと物語を単一のドキュメントに融合することで思考を整理し、コメントが達成できない方法でコードを文書化し、レポート作成の自動化を支援します。処理する。

したがって、データサイエンティストを管理している場合は、knitr http://yihui.name/knitr/およびipythonノートブックhttp://ipython.org/notebook.htmlをお勧めします。これらのツールは、分析とレポートを結び付けます。そして、簡単に習得できます。

レポートの内容に関しては、思い浮かぶいくつかの他の推奨事項。

符号、大きさ、単位を確認してください。兆候を確認するということは、あなたの効果があなたが期待する方向にあることを確認することを意味します。また、単に係数を報告する以上のことをするように管理者に依頼することを強制するのにも役立ちます。他の既知の効果（以前の講義で説明されている）と比較して大きさを確認することは、奨励するのに本当に良いことです。最後に、すべての単位（グラフの軸、係数、平均など）を配置し、単位を必ず理解してください。この小さなステップが何回役立ったのかはお伝えできません。

あなたが管理するデータサイエンティストやアナリストに専門的な専門用語を話させて解釈と解釈可能性を持たせることが重要です。前者については、他の既知の効果と比較するというこの考えを繰り返します。第二に、私は**効果批判**のアイデアを奨励します。これは、効果に興奮するのではなく、最大の批評家になるという考え方です。それが偽である可能性のある考えられるすべての理由を把握してみてください。これは、ほとんどの場合、実行すべき新しい分析につながります。最後に、解釈可能性のために、解釈可能なパラメーターを持つ最小限の(parsimonious)なモデルを奨励します。つまり、シンプルさを重視します。もちろん、これは、新しい最小限の(parsimonious)な知識を作成しようとしているデータサイエンスの実験により興味がある場合です。予測のみを改善しようとすると状況が変わります（最初の講義を参照）。

最後に、**バージョン管理**は一般的な良い習慣です。バージョン管理は、ソフトウェア、コード、データ、およびレポートのバージョンを保持するプロセスです。最新のバージョン管理ソフトウェアは、このプロセスを簡単にします。適切なバージョン管理を使用すると、プロジェクトを前のステップに戻すことができ、すべてのステップにコメントが付けられます。**git**のようなツールは、多くの人が同じプロジェクトに取り組んでいる大規模に分散した設定でこれを可能にします。Gitはバージョン管理ソフトウェアであり、**gitリポジトリ**は実際のバージョン管理データベースです。gitリポジトリでのコラボレーションはサーバーで発生します。幸いなことに、一般用およびビジネス用のホストされたGitサーバーがたくさんあります。最大のものはgithub https://github.com/ですただし、bitbucketのような他のものもhttps://bitbucket.org/に最適です。これらは、サーバーへの素晴らしいWebインターフェースも提供します。gitには、https： //git-scm.com/book/en/v2を使用するための完全な無料の本と、100万のオンラインチュートリアルがあります。

もちろん、gitは多くのバージョン管理システムの1つです。主なポイントは、組織内のバージョン管理文化を推奨（または要求/強制）することです。


