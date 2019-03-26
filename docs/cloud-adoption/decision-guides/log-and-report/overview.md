---
title: CAF:ログとレポートの意思決定ガイド
titleSuffix: Microsoft Cloud Adoption Framework for Azure
ms.service: architecture-center
ms.subservice: enterprise-cloud-adoption
ms.custom: governance
ms.date: 02/11/2019
description: Azure 移行のコア サービスとしてのログ、レポート、および監視について学習します。
author: rotycenh
ms.openlocfilehash: 36552488872622ec59e2fcf4816da4184c3d4fbf
ms.sourcegitcommit: 273e690c0cfabbc3822089c7d8bc743ef41d2b6e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55901718"
---
# <a name="logging-and-reporting-decision-guide"></a>ログとレポートの意思決定ガイド

パフォーマンス、アップタイム、およびセキュリティの問題が重大な問題になる前に、IT チームに通知するメカニズムは、すべての組織に必要です。 成功した監視戦略では、ワークロードとネットワーク インフラストラクチャを構成する個々のコンポーネントがどのように実行されているかを把握することができます。 パブリック クラウドの移行では、ログとレポートを既存の任意の監視システムと統合しつつ、重要なイベントとメトリックを適切な IT スタッフに明らかにすることは、組織がアップタイム、セキュリティ、およびポリシーのコンプライアンス目標を確実に達成するうえで非常に重要です。

![ログ、レポート、および監視のオプションを、簡単なものから非常に複雑なものまで、以下のリンクに合わせてプロット](../../_images/discovery-guides/discovery-guide-logs-and-reporting.png)

ジャンプ先:[監視インフラストラクチャの計画](#planning-your-monitoring-infrastructure) | [クラウド ネイティブ](#cloud-native) | [オンプレミスの拡張機能](#on-premises-extension) | [ゲートウェイ集約](#gateway-aggregation) | [ハイブリッド監視 (オンプレミス)](#hybrid-monitoring-on-premises) | [ハイブリッド監視 (クラウド ベース)](#hybrid-monitoring-cloud-based) | [マルチクラウド](#multi-cloud) | [詳細情報](#learn-more)

クラウド ID 戦略を決定するときの変曲点は、主に組織が運用プロセスに行ってきた既存の投資に基づき、マルチクラウド戦略をサポートするために必要な任意の要件もある程度関係します。

クラウドでのアクティビティをログに記録してレポートを作成するには、複数の方法があります。 クラウド ネイティブと一元化されたログには、サブスクリプション設計とサブスクリプションの数に基づく 2 つの共通のサービスとしてのソフトウェア (SaaS) オプションがあります。

## <a name="planning-your-monitoring-infrastructure"></a>監視インフラストラクチャの計画

デプロイを計画するときには、ログ データの格納場所と、クラウド ベースのレポート サービスと監視サービスを既存のプロセスとツールに統合する方法を検討する必要があります。

| 質問 | クラウド ネイティブ | オンプレミスの拡張機能 | ハイブリッド監視 | ゲートウェイ集約 |
|-----|-----|-----|-----|-----|
| 既存のオンプレミスの監視インフラストラクチャはありますか? | いいえ  | 可能  | はい |  いいえ  |
| ログ データの外部の保存場所への格納を妨げている要件はありますか? | いいえ  | はい | いいえ  | いいえ  |
| クラウド監視とオンプレミス システムを統合する必要がありますか? | いいえ  | いいえ  | はい | いいえ  |
テレメトリ データを監視システムに送信する前に、処理またはフィルター処理する必要がありますか? | いいえ  | いいえ  | いいえ  | はい |

### <a name="cloud-native"></a>クラウド ネイティブ

現在、組織に確立されたログとレポートのシステムがない場合、または計画されたクラウドのデプロイで既存のオンプレミスの監視システムまたは他の外部の監視システムとの統合が必要ない場合は、クラウド ネイティブの SaaS ソリューションが最も簡単な選択です。

このシナリオでは、ログ データが記録され、ワークロードと同じクラウド環境に格納され、同時に情報を処理して IT スタッフに明らかにするログ ツールとレポート作成ツールが、クラウド プラットフォームの一部として提供されます。

クラウド ネイティブのログ記録ソリューションは、サブスクリプションごとに、またはより小さい実験的なデプロイにはワークロードごとにアドホックで実装でき、クラウド全体でログ データを監視するための一元化された方法で構成することができます。

**クラウド ネイティブの前提条件**。 クラウド ネイティブのログとレポートのシステムの使用には、次の前提条件があります。

- クラウド ワークロードから既存のオンプレミス システムにログを統合する必要がない。
- オンプレミス システムの監視に、クラウド ベースのレポート システムを使用する予定がない。

### <a name="on-premises-extension"></a>オンプレミスの拡張機能

クラウドのテレメトリを、ハイブリッドのログとレポートをサポートしていない、または最小限の再デプロイでアプリケーションとサービスの移行をサポートするオンプレミス システムと統合する必要があるシナリオでは、ログ データをクラウド環境に格納するのではなく、オンプレミス システムに直接送信する VM に監視エージェントをデプロイする必要があります。

このアプローチをサポートするためには、[ハイブリッド ネットワーク](../software-defined-network/hybrid.md)と[クラウドでホストされるドメイン サービス](../identity/overview.md#cloud-hosted-domain-services)を組み合わせることで、クラウド リソースがオンプレミス システムと直接通信できるようにする必要があります。 これを実施することで、クラウド仮想ネットワークがオンプレミス環境のネットワーク拡張機能として機能します。 そのため、クラウドでホストされるワークロードは、オンプレミスのログおよびレポートのシステムと直接通信できます。

このアプローチでは、クラウドにデプロイされたアプリケーションまたはサービスを少し変更して、監視ツールへの既存の投資を利用します。 多くの場合、これはリフトアンドシフト移行時に監視をサポートする最も速いアプローチです。 ただし、クラウド ベースの PaaS および SaaS のリソースによって生成されたログ データはキャプチャされず、VM の状態など、クラウド プラットフォーム自体で生成された VM 関連のログはすべて省略されます。 その結果、このパターンは、より包括的なハイブリッド監視ソリューションが実装されるまでの一時的な解決策とする必要があります。

オンプレミスのみの前提条件:

- 技術的な要件をサポートするため、または規制やポリシー要件により、ログ データのみをオンプレミス環境でのみ維持する必要がある。
- オンプレミス システムでハイブリッドのログとレポート、またはゲートウェイ集約ソリューションをサポートしていない。
- クラウド ベースのアプリケーションで、オンプレミスのログ システムにテレメトリを直接送信できるか、オンプレミスに送信する監視エージェントをワークロード VM にデプロイできる。
- ワークロードが、クラウド ベースのログとレポートを必要とする PaaS または SaaS サービスに依存していない。

### <a name="gateway-aggregation"></a>ゲートウェイ集約

クラウド ベースのテレメトリ データの量が非常に大きい、または既存のオンプレミスの監視システムで、ログ データが処理できるように事前に変更する必要があるシナリオでは、ログ データの[ゲートウェイ集約](../../../patterns/gateway-aggregation.md)サービスが必要になる場合があります。

ゲートウェイ サービスは、クラウド プロバイダーにデプロイされます。 次に、関連するアプリケーションとサービスは、既定のログ システムではなく、ゲートウェイにテレメトリ データが送信されるように構成されます。 ゲートウェイで集約、結合などのデータの処理ができるようになります。それ以外の場合は、取り込みと分析のために監視サービスにデータを送信する前に、データを書式設定できます。

また、ゲートウェイを使用して、クラウド ネイティブまたはハイブリッド システムにバインドされたテレメトリ データを集約または前処理することもできます。

ゲートウェイ集約の前提条件:

- ご使用のクラウド ベースのアプリケーションまたはサービスから非常に高いレベルのテレメトリ データを想定している。
- テレメトリ データを監視システムに送信する前に、書式設定するか、最適化する必要がある。
- 監視システムに、ゲートウェイで処理された後にログ データを取り込むのに使用できる API またはその他のメカニズムがある。

### <a name="hybrid-monitoring-on-premises"></a>ハイブリッド監視 (オンプレミス)

ハイブリッド監視ソリューションでは、オンプレミスとクラウドの両方のリソースからのログ データを結合して、IT 資産の運用状態に関する統合ビューを提供します。

置換が難しいまたは置換にコストがかかるオンプレミスの監視システムへの既存の投資がある場合、クラウド ワークロードからのテレメトリを以前から存在している監視ソリューションに統合する必要がある場合があります。 ハイブリッドのオンプレミスの監視システムでは、オンプレミスのテレメトリ データは引き続き既存のオンプレミスの監視システムを使用します。 クラウド ベースのテレメトリ データは、クラウド監視システムに直接送信されるか、ワークロードと共にクラウドに格納されてから、一定の間隔でコンパイルされ、オンプレミス システムに取り込まれます。

**オンプレミスのハイブリッド監視の前提条件**。 ハイブリッド監視にオンプレミスのログとレポートのシステムを使用するには、次の前提条件があります。

- クラウドのワークロードを監視するため、既存のオンプレミスのレポート システムを使用する必要がある。
- ログ データの所有権をオンプレミスで維持する必要がある。
- オンプレミスの管理システムに、クラウド ベースのシステムからログ データを取り込むために使用できる API またはその他のメカニズムがある。

> [!TIP]
> クラウド移行の反復的な性質の一環として、個別のクラウド ネイティブおよびオンプレミスの監視から部分的なハイブリッド アプローチへの移行はあり得ます。 監視アーキテクチャに対する変更が IT および運用の全体のプロセスに沿っていることを確認します。

### <a name="hybrid-monitoring-cloud-based"></a>ハイブリッド監視 (クラウド ベース)

オンプレミスの監視システムを維持する切実なニーズがない場合、またはオンプレミスの監視システムを SaaS ソリューションと置き換える場合、オンプレミスのログ データを一元化されたクラウド ベースの監視システムと統合することもできます。

オンプレミスを中心としたアプローチをミラーリングすることで、このシナリオではクラウド ワークロードがその既定のクラウド ログ メカニズムを使用します。また、オンプレミスのアプリケーションとサービスは、テレメトリをクラウドベースのログ システムに直接送信するか、そのデータを集約してクラウド システムに一定間隔で読み込みます。 その後、クラウド ベースの監視システムは、IT 資産全体の監視とレポートのプライマリ システムとして機能します。

クラウドベースのハイブリッド監視の前提条件:ハイブリッド監視にクラウドベースのログとレポートのシステムを使用するには、次の前提条件があります。

- 既存のオンプレミスの監視システムに依存していない。
- ワークロードにログ データをオンプロミスで格納するための規制やポリシー要件がない。
- クラウド ベースの管理システムに、オンプレミスのアプリケーションとサービスからログ データを取り込むために使用できる API またはその他のメカニズムがある。

### <a name="multi-cloud"></a>マルチクラウド

ログとレポートの機能をマルチクラウド プラットフォーム全体に取り込むのは、複雑になる場合があります。 プラットフォーム間で提供されるサービスは多くの場合、直接比較することはできず、これらのサービスで提供されるログとテレメトリの機能も異なります。
マルチクラウドのログのサポートでは多くの場合、ハイブリッドのログ記録ソリューションにデータを送信する前に、一般的な形式にログ データを処理するゲートウェイ サービスを使用する必要があります。

## <a name="learn-more"></a>詳細情報

[Azure Monitor](/azure/azure-monitor/overview) は Azure の既定のレポートと監視サービスです。 共有サービスには次のものが含まれています。

- アプリのテレメトリ、ホストのテレメトリ (VM など)、コンテナー メトリック、Azure プラットフォームのメトリック、イベント ログを収集するための統合プラットフォーム。
- 視覚化ツール、クエリ ツール、アラート ツール、分析ツール。 仮想マシン、ゲスト オペレーティング システム、仮想ネットワーク、およびワークロードのアプリケーション イベントの分析情報を提供できます。
- 外部サービスとの統合および監視とアラート サービスの自動化のための [REST API](/azure/monitoring-and-diagnostics/monitoring-rest-api-walkthrough)。
- 多くの人気のあるサード パーティ ベンダーとの[統合](/azure/monitoring-and-diagnostics/monitoring-partners)。