
---
title: Power BI ワークスペースについて ~クラシックワークスペースと新しい(アプリ)ワークスペース~
date: 2021-07-30 00:00:00 
tags:
  - Power BI
  - Workspace
---

こんにちは、Power BI サポート チームです。

Power BIにおいて、レポートやダッシュボードを部署やチームメンバーに共有する際に不可欠なワークスペース。
多くのPower BI ユーザーの方に利用されている機能です。

この"ワークスペース"ですが、ここ数年において様々なアップデートがリリースされており、2021 年7 月時点では"クラシックワークスペース"と"新しい(アプリ)ワークスペース"の2 種類が並行して利用できる状態となっています。

今回は、この二つのワークスペースの違いと今後ワークスペースがどう進化していくのか、Power BI 管理者が事前に確認しておくべき設定をご紹介いたします。

<br>

> [!IMPORTANT]
> 本記事は 弊社公式ブログ「Microsoft Power BI ブログ」の公開情報を元に構成しておりますが、本記事編集時点と実際の機能やリリース時期に相違がある場合がございます。
>元記事は以下よりご確認ください（英語）
><Span style="font-size: 90%">[Updated timeline for upgrading classic workspaces](https://powerbi.microsoft.com/ja-jp/blog/updated-timeline-for-upgrading-classic-workspaces/)</span>

<br>

## サマリー
---
-   Power BI では、2021 年7 月時点で2 種類のワークスペースが利用できます。クラシックワークスペースはMicrosoft 365 グループに紐づくワークスペース、新しい(アプリ)ワークスペースは業務に合わせてメンバーやロールを柔軟にカスタマイズできるワークスペースです。
<br>
-   クラシックワークスペースは2022 年10 月頃に作成機能を廃止し、2022 年4 月頃に既存のワークスペースも含めすべて新しい(アプリ)ワークスペースへ自動アップグレードする予定です。
<br>
-   2021 年7 月にPower BI 管理者向けに全てのクラシックワークスペースを新しい(アプリ)ワークスペースにアップグレードする機能が追加されました。
<br>
-   新しい(アプリ)ワークスペースに手動でアップグレードする際は、従来の権限がそのまま移行するため、追加で権限変更の作業はなく、ワークスペースの使用者側でも必要な作業はありません。
<br>
-   自動アップグレードまでに、ワークスペースの手動アップグレードをご検討ください。
<br>


## 目次
---
1.  クラシックワークスペースと新しい(アプリ)ワークスペース
2.  クラシックワークスペースが使えなくなる？今後のワークスペースの開発ロードマップ
3.  Power BI 管理者が確認しておくべき設定

<br>


## 1. クラシックワークスペースと新しい(アプリ)ワークスペース
---
Power BI におけるワークスペースは、文字通り一つのオフィスのようなものです。
ワークスペースに参加したメンバーが共同作業できるスペースとして、配置されたデータセットをもとにレポートやダッシュボードを作成し、共有することができます。

前述のとおり、2021 年7 月時点では”クラシックワークスペース”と”新しい(アプリ)ワークスペース”の2 種類が並行して利用できる状態となっています。それぞれの特徴についてご紹介していきます。 

</br>

### クラシックワークスペース


従来からPower BI で機能しているワークスペースのことを指します。（余談ですがクラシックは「古典」「前世代の」という意味がありますね）

クラシックワークスペースはMicrosoft 365 グループ（以下、M365 グループ）に基づくワークスペースです。

これは、Power BI 側でワークスペースを作成すれば、同じ名前とメンバー構成のM365 グループが作成され、M365 グループを削除すれば、Power BI 側で同名のワークスペースが削除される、鏡のような表裏一体の関係になっています。

<div align="center">
<img src="blog_workspace_001.png" alt="画像1_クラシックワークスペースについて" title="画像1_クラシックワークスペースについて">
</div>

クラシックワークスペースでは、グループを作成すればすぐに同じ構成のワークスペースが作成されるという点で、グループ管理がしやすい利点はありますが、片方だけで良いのに意図しないワークスペースやグループが作成されることが扱いづらいという点もあります。 

また、セキュリティグループや配布グループといったその他のグループやM365 グループ以外の個人を招待することもできなかったため、粒度の細かいワークスペース設定ができないという欠点もあります。 

<br>

### 新しい(アプリ)ワークスペース

2019 年4 月以降に一般公開されたワークスペースのことを指します。一般公開以降、ワークスペースを作成する際の既定の設定は新しい(アプリ)ワークスペースとなっています。

クラシックワークスペースのように、M365 グループとの表裏一体の機能はなくなりました。その代わり、自由にメンバーの入れ替えができたり、複数グループを同じワークスペースに追加することができたりと、ワークスペースのカスタマイズ性が向上しました。

下図はクラシックワークスペースと新しい(アプリ)ワークスペースの主な特徴の比較表になります。

| 比較                                           | クラシックワークスペース                                                                                      | 新しい(アプリ)ワークスペース                                                                                                                                                                 | 
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | 
| 一言で表すと…                                 | M365 グループに紐付いたワークスペース                                                                         | 業務に合わせてメンバーやロールを柔軟にカスタマイズできるワークスペース                                                                                                               | 
| 参加者                                         | M365 グループに連動                                                                                           | 個人～グループレベルで追加削除が可能（M365 グループとは非連動）<br>グループレベルでは従来のM365 グループに加えて、セキュリティグループ、配布リストにアクセス許可を付与することも可能 | 
| ゲストユーザの設定                             | M365 グループに追加することで招待可能                                                                         | ワークスペース単位で招待可能                                                                                                                                                         | 
| ワークスペースの作成制限                       | M365 グループを作成できるユーザの管理で制限可能<br><span style="font-size: 80%; color: black;">参考：[Microsoft 365 グループを作成できるユーザーを管理する](https://docs.microsoft.com/ja-jp/microsoft-365/solutions/manage-creation-of-groups)</span> | Power BI 管理ポータルから組織全体・特定ユーザ・無効化の設定が可能                                                                                                                    | 
| 参加者のロール                                 | 管理者・メンバーの設定が可能<br>さらにメンバーへコンテンツの編集または表示のみのどちらかを選択可能            | 管理者・メンバー・共同作成者・ビューアーの4種類の設定が可能<br><span style="font-size: 80%; color: black;">参考：[新しい(アプリ)ワークスペースのロール](https://docs.microsoft.com/ja-jp/power-bi/collaborate-share/service-new-workspaces#roles-in-the-new-workspaces)</span>                                                                                    | 
| ワークスペース外へのデータセット共有           | 不可                                                                                                          | 別のワークスペースにデータセットを共有可能<br><span style="font-size: 80%; color: black;">参考：[共有データセットのビルド アクセス許可](https://docs.microsoft.com/ja-jp/power-bi/connect-data/service-datasets-build-permissions)</span>                                                                                            | 
| ワークスペースアクティビティ通知の連絡先リスト | なし                                                                                                          | 通知ユーザーの指定が可能                                                                                                                                                             | 
| 組織アプリ                                     | インストール・発行：○                                                                                        | インストール・発行：○                                                                                                                                                               | 
| テンプレートアプリ                             | インストール：○<br>発行：×                                                                                   | インストール：○<br>発行：○                                                                                                                                                         | 

2021 年7 月時点

<br>

## 2.  クラシックワークスペースが使えなくなる？今後のワークスペースの開発ロードマップ
---
現時点ではクラシックワークスペースと新しい(アプリ)ワークスペースがそれぞれ並行利用できる状態ですが、Power BI の開発ロードマップでは、クラシックワークスペースが2022 年4 月頃に終了し、既存のクラシックワークスペースは自動的に新しい(アプリ)ワークスペースにアップグレードされる予定となっています。

またアプリと類似する機能を持っていたコンテンツパックは2021 年2 月以降、作成・編集機能が削除、4 月以降は機能そのものが終了しました。代替として新しい(アプリ)ワークスペースでのアプリ利用、共有データセットの利用をご検討ください。

### クラシックワークスペースの移行に関する今後の開発アイテム
<br>

| 開発アイテム                                                         | 詳細                                                                                                                                                                  | 状況            | 
| -------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------- | 
| クラシックワークスペースのアップグレード機能                         | 既存のクラシックワークスペースを新しい(アプリ)ワークスペースにアップグレードにすることができるようになりました<br><span style="font-size: 80%; color: black;">参考：[クラシック ワークスペースをアップグレードする](https://docs.microsoft.com/ja-jp/power-bi/collaborate-share/service-upgrade-workspaces)</span> | 利用可能        | 
| Power BI 管理者によるクラシックワークスペースの作成のブロック機能    | 新しいクラシックワークスペースが作成されることを防ぐ機能を管理者が設定することができるようになりました<br><span style="font-size: 80%; color: black;">参考：[クラシック ワークスペースの作成をブロックする](https://docs.microsoft.com/ja-jp/power-bi/collaborate-share/service-create-workspaces)</span>         | 利用可能        | 
| 全テナントのクラシックワークスペースの作成のブロックの有効化切り替え | Power BIのすべてのテナントで"クラシックワークスペースの作成のブロック"が有効化となりました。2021年7月現在では管理ポータルよりブロックを再度無効に戻すことが可能です   | 2021年1月~      | 
| コンテンツパックの新規作成・編集機能の提供終了                       | 2021年2月 コンテンツパックの新規作成・編集機能が終了しました                                                                                                                            | 2021年2月~      | 
| Power BI 管理者によるクラシックワークスペースのアップグレード        | 管理ポータルのワークスペースリストより、ワークスペースのアップグレードが一括で実施することができるようになりました<br><span style="font-size: 80%; color: black;">参考：[Power BI 管理ポータル](https://docs.microsoft.com/ja-jp/power-bi/admin/service-admin-portal)</span>                     | 2021年6月~      | 
| Power BI管理者用による全てのクラシックワークスペースのアップグレード | Power BI管理ポータルで管理者がすべてのクラシックワークスペースをアップグレードできるようになる予定です                                                                | 2021年7月~ | 
| クラシックワークスペースの作成機能の提供終了                         | クラシックワークスペース作成機能が終了する予定です。またテナント設定の"クラシックワークスペースの作成のブロック"の設定もPower BI 管理ポータルから削除される予定です   | 2021年10月予定  | 
| コンテンツパック機能の削除                                           | コンテンツパック機能は2021年10月にPower BIサービスから削除される予定です                                                                                              | 2021年10月予定  | 
| クラシックワークスペース機能の提供終了と自動アップグレード           | クラシックワークスペース機能の提供が終了し、すべてのクラシックワークスペースが自動的に新しい(アプリ)ワークスペースへアップグレードされる予定です                      | 2022年4月予定   | 

※2021 年7 月時点
<br>

## 3.  Power BI 管理者が確認しておくべき設定
---
新しい(アプリ)ワークスペースに切り替えていく中で、事前に確認しておくべき管理ポータルの設定についていくつか紹介いたします。

### 3-1. テナント設定

<div align="center">
<img src="blog_workspace_002.png" alt="画像2_テナント設定" title="画像2_テナント設定">
</div>

#### ①ワークスペースの作成（アプリワークスペース エクスペリエンス）

従来ではクラシックワークスペースはM365 グループに紐づいていましたが、新しい(アプリ)ワークスペースは、管理ポータルより作成許可をコントロールすることができるようになります。
既定の設定では「Office365 でグループを作成するアクセス許可」によってコントロールされています。
もし2019 年4 月以前から一度もこの設定を変更していない場合、以下のように注意が表示されることがあります。

この場合、適用を押下することで初めて変更され組織全体でワークスペースが作成できるようになります。

<div align="center">
<img src="blog_workspace_003.png" alt="画像3_新しいワークスペース" title="画像3_新しいワークスペース">
</div>

#### ②クラシックワークスペースの作成のブロック

この設定を有効にすると、ユーザはPower BI サービスやAPI を通じてクラシックワークスペースを作成することができなくなります。ブロック有効後に新しく作成された M365 グループのクラシックワークスペースは作成されなくなりますが、有効前の既存のクラシックワークスペースは、この設定の影響を受けず、引き続き利用が可能です。
ブロック有効後に新しく作成されたM365 グループのクラシックワークスペースを利用したい場合は、ブロックを無効に変更することでクラシックワークスペースが表示されるようになります。

また、この機能は新しい(アプリ)ワークスペースの利用を促進するため、2021 年1
月より全テナントでブロックが\"有効化\"となりました。引き続きクラシックワークスペースとM365 グループの連動を行いたい場合、\"無効\"に戻す必要があります。

<div align="center">
<img src="blog_workspace_004.png" alt="画像4_クラシックブロックの挙動" title="画像4_クラシックブロックの挙動">
</div>

<br>

### 3-2. ワークスペース

テナントに存在するワークスペースをリストで一覧表示ができる設定画面です。
新しい(アプリ)ワークスペースは M365 グループと連動しないため、管理されていないワークスペースが発生しないよう、この設定画面から一元管理ができるようになっています。この画面では、Power BI 管理者は新しい(アプリ)ワークスペース管理者を割り当てたり、ワークスペースからユーザーを追加/削除したりすることができます。クラシックワークスペースの管理については、引き続きMicrosoft 365 管理センターを使用することになります。

<div align="center">
<img src="blog_workspace_005.png" alt="画像5_ワークスペース設定" title="画像5_ワークスペース設定">
</div>

<br>

以上、本ブログ が少しでも皆様のお役に立てますと幸いでございます。 



