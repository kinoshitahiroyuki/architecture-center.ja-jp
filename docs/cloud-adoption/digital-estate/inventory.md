---
title: CAF:デジタル資産のインベントリ データを収集する
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: デジタル資産のインベントリを収集する方法。
author: BrianBlanchard
ms.date: 12/10/2018
ms.topic: guide
ms.service: architecture-center
ms.subservice: enterprise-cloud-adoption
ms.openlocfilehash: 0c68ff1e5ff51395698d37fb9b59c7a76c9479b7
ms.sourcegitcommit: c053e6edb429299a0ad9b327888d596c48859d4a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "58242553"
---
# <a name="gather-inventory-data-for-a-digital-estate"></a>デジタル資産のインベントリ データを収集する

インベントリを作成することは、[デジタル資産計画](overview.md)の最初の手順です。 このプロセスでは、後で分析や合理化が可能なように、特定のビジネス機能をサポートする IT 資産の一覧が収集されます。 この記事では、計画の必要上、分析にはボトムアップの手法を採用することが最適だと想定しています。 詳細については、[デジタル資産計画の手法](./approach.md)についての記事を参照してください。

## <a name="take-inventory-of-a-digital-estate"></a>デジタル資産のインベントリの収集

デジタル資産をサポートするインベントリは、目的としているデジタル変革と、それに対応する変革の過程に応じて変わります。

- **事業の変革:**  事業の変革の際には、多くの場合、すべての VM とサーバーの一元的な一覧を作成できるスキャン ツールからインベントリを収集することが推奨されます。 一部のツールでは、ネットワーク マッピングや依存関係も作成できます。これは、ワークロードの配置を定義するのに役立ちます。

- **増分型の変革:**  増分型の変革でのインベントリは、顧客と共に始まります。 開始から終了まで顧客のエクスペリエンスをマッピングすることが、良い開始点となります。 そのマップをアプリケーション、API、データ、およびその他の資産に対応付けることで、分析用の詳細なインベントリが作成されます。

- **中断を伴う変革**:  中断を伴う変革では、製品やサービスに重点が置かれます。 そうした観点から、インベントリには、市場や必要とされる機能に中断をもたらす機会のマッピングが含められます。

## <a name="accuracy-and-completeness-of-an-inventory"></a>インベントリの精度と完全性

インベントリは、初回の実施時に完全であることはめったにありません。 クラウド戦略チームのさまざまなメンバーが、利害関係者とパワー ユーザーの足並みを揃えさせて、インベントリを検証することを強くお勧めします。 可能であれば、ネットワークと依存関係の分析などのその他のツールを利用すると、トラフィックの送信先になっているがインベントリに含まれていない資産を識別できます。

## <a name="next-steps"></a>次の手順

インベントリの作成と検証が終わったら、インベントリを合理化できます。 インベントリの合理化は、デジタル資産計画の次の手順です。

> [!div class="nextstepaction"]
> [デジタル資産を合理化する](rationalize.md)