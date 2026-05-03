📌概要
目的ーオンライン購買データを用いて顧客の行動を分析、売り上げ構造を明らかにする。
評価するーRFM分析を用いて顧客をセグメント化し、それぞれの顧客層が売り上げにどのように貢献しているか評価

🎯目的
・VIP特定
・顧客の分布構造の把握
・セグメント別の売り上げ貢献度の可視化

📥入力データ
データセット	Online Retail.xlsx
内容			オンライン購買履歴データ
主なカラム
customer id 
invoice date 
invoice no 
quantity 
unitprice

⚙️分析手法
処理フロー
データ入力
→売り上げ計算
→顧客単位で集計（最新購入日、合計購入回数、合計購入金額）
→RFM指標産出
→セグメント分類
→可視化

・RFM定義
Retency（最新性）	最新購買日からの経過日数 = データ内の最新日 - 最終購入日
Frequency（頻度）	購入回数
Monetary（金額）		総購入金額

・集計要件
顧客IDごとに集計（最新購入日、合計購入回数、合計購入金額）
最新購入日	Invoicedateの最新日時
合計購入回数	Invoicenoをカウント
合計購入金額	UnitPrice * Quantity =　TotalSalesとし、TotalSalesを合計

・セグメント設計
RMFをそれぞれ4つの四分位セグメントグループ(qcut)に均等数に分配。
VIP	Recency、Monetary、Frequencyがすべて上位2グループの集団
Middle	VIP、At risk以外
At risk	Recencyが最下位でFrequencyが中央値以下の集団

・出力
棒グラフ
	セグメント（VIP客、中間層、危険層）ごとの売り上げグラフ
	セグメントごとの購買回数グラフ
円グラフ
	セグメントごとの売り上げの割合グラフ（円グラフ）