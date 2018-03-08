---
title: "データ ストレージ テクノロジの選択"
description: 
author: zoinerTejada
ms:date: 02/12/2018
ms.openlocfilehash: d8f831e758ddc8604758392644a68b56dc51cf57
ms.sourcegitcommit: 475064f0a3c2fac23e1286ba159aaded287eec86
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="choosing-a-big-data-storage-technology-in-azure"></a><span data-ttu-id="fd65c-102">Azure でのビッグ データ ストレージ テクノロジの選択</span><span class="sxs-lookup"><span data-stu-id="fd65c-102">Choosing a big data storage technology in Azure</span></span>

<span data-ttu-id="fd65c-103">このトピックでは、[分析データ ストア](./analytical-data-stores.md)や[リアルタイムのストリーミング取り込み](./real-time-ingestion.md)とは対照的に、ビッグ データ ソリューション向けのデータ ストレージ オプション (具体的には、一括データ インジェストとバッチ処理用のデータ ストレージ) を比較します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-103">This topic compares options for data storage for big data solutions &mdash; specifically, data storage for bulk data ingestion and batch processing, as opposed to [analytical data stores](./analytical-data-stores.md) or [real-time streaming ingestion](./real-time-ingestion.md).</span></span>

## <a name="what-are-your-options-when-choosing-data-storage-in-azure"></a><span data-ttu-id="fd65c-104">Azure でデータ ストレージを選択するときのオプション</span><span class="sxs-lookup"><span data-stu-id="fd65c-104">What are your options when choosing data storage in Azure?</span></span>

<span data-ttu-id="fd65c-105">必要に応じて、Azure にデータの取り込むためのさまざまなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fd65c-105">There are several options for ingesting data into Azure, depending on your needs:</span></span>

<span data-ttu-id="fd65c-106">**File Storage**</span><span class="sxs-lookup"><span data-stu-id="fd65c-106">**File storage**</span></span>

- [<span data-ttu-id="fd65c-107">Azure Storage BLOB</span><span class="sxs-lookup"><span data-stu-id="fd65c-107">Azure Storage blobs</span></span>](/azure/storage/blobs/storage-blobs-introduction)
- [<span data-ttu-id="fd65c-108">Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="fd65c-108">Azure Data Lake Store</span></span>](/azure/data-lake-store/)

<span data-ttu-id="fd65c-109">**NoSQL データベース**</span><span class="sxs-lookup"><span data-stu-id="fd65c-109">**NoSQL databases**</span></span>

- [<span data-ttu-id="fd65c-110">Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="fd65c-110">Azure Cosmos DB</span></span>](/azure/cosmos-db/)
- [<span data-ttu-id="fd65c-111">HDInsight での HBase</span><span class="sxs-lookup"><span data-stu-id="fd65c-111">HBase on HDInsight</span></span>](http://hbase.apache.org/)

## <a name="azure-storage-blobs"></a><span data-ttu-id="fd65c-112">Azure Storage BLOB</span><span class="sxs-lookup"><span data-stu-id="fd65c-112">Azure Storage blobs</span></span>

<span data-ttu-id="fd65c-113">Azure Storage は、高い可用性セキュリティ、耐久性、スケーラビリティ、および冗長性を備えた管理対象ストレージ サービスです。</span><span class="sxs-lookup"><span data-stu-id="fd65c-113">Azure Storage is a managed storage service that is highly available, secure, durable, scalable, and redundant.</span></span> <span data-ttu-id="fd65c-114">メンテナンスや重大な問題には、Microsoft がお客様に代わって対処します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-114">Microsoft takes care of maintenance and handles critical problems for you.</span></span> <span data-ttu-id="fd65c-115">Azure Storage は、Azure が提供する最大のユビキタス ストレージ ソリューションであり、多数のサービスとツールと連携させて使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-115">Azure Storage is the most ubiquitous storage solution Azure provides, due to the number of services and tools that can be used with it.</span></span>

<span data-ttu-id="fd65c-116">データの格納に使用できるさまざまな Azure Storage サービスがあります。</span><span class="sxs-lookup"><span data-stu-id="fd65c-116">There are various Azure Storage services you can use to store data.</span></span> <span data-ttu-id="fd65c-117">多数のデータ ソースから BLOB を格納するための最も柔軟なオプションは、[BLOB ストレージ](/azure/storage/blobs/storage-blobs-introduction)です。</span><span class="sxs-lookup"><span data-stu-id="fd65c-117">The most flexible option for storing blobs from a number of data sources is [Blob storage](/azure/storage/blobs/storage-blobs-introduction).</span></span> <span data-ttu-id="fd65c-118">BLOB は、基本的にはファイルです。</span><span class="sxs-lookup"><span data-stu-id="fd65c-118">Blobs are basically files.</span></span> <span data-ttu-id="fd65c-119">それらは、画像、ドキュメント、HTML ファイル、仮想ハード ディスク (VHD) から、ログなどのビッグ データ、データベースのバックアップまで、ほぼすべてを格納できます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-119">They store pictures, documents, HTML files, virtual hard disks (VHDs), big data such as logs, database backups &mdash; pretty much anything.</span></span> <span data-ttu-id="fd65c-120">BLOB は、フォルダーに似たコンテナーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-120">Blobs are stored in containers, which are similar to folders.</span></span> <span data-ttu-id="fd65c-121">コンテナーは、BLOB のセットをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-121">A container provides a grouping of a set of blobs.</span></span> <span data-ttu-id="fd65c-122">ストレージ アカウントに含めることができるコンテナーの数には制限がなく、1 つのコンテナーに格納できる BLOB の数にも制限はありません。</span><span class="sxs-lookup"><span data-stu-id="fd65c-122">A storage account can contain an unlimited number of containers, and a container can store an unlimited number of blobs.</span></span>

<span data-ttu-id="fd65c-123">Azure Storage は、柔軟性、高可用性、および低コストという理由で、ビッグ データと分析ソリューションに適した選択肢です。</span><span class="sxs-lookup"><span data-stu-id="fd65c-123">Azure Storage is a good choice for big data and analytics solutions, because of its flexibility, high availability, and low cost.</span></span> <span data-ttu-id="fd65c-124">さまざまなユース ケース用のホット、クール、およびアーカイブ ストレージ層を提供します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-124">It provides hot, cool, and archive storage tiers for different use cases.</span></span> <span data-ttu-id="fd65c-125">詳細については、「[Azure Blob Storage: ホット、クール、アーカイブ ストレージ層](/azure/storage/blobs/storage-blob-storage-tiers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd65c-125">For more information, see [Azure Blob Storage: Hot, cool, and archive storage tiers](/azure/storage/blobs/storage-blob-storage-tiers).</span></span>

<span data-ttu-id="fd65c-126">Azure Blob Storage は、Hadoop からアクセスできます (HDInsight から利用できます)。</span><span class="sxs-lookup"><span data-stu-id="fd65c-126">Azure Blob storage can be accessed from Hadoop (available through HDInsight).</span></span> <span data-ttu-id="fd65c-127">HDInsight は、クラスターの既定のファイル システムとして Azure Storage 内の BLOB コンテナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-127">HDInsight can use a blob container in Azure Storage as the default file system for the cluster.</span></span> <span data-ttu-id="fd65c-128">HDInsight のすべてのコンポーネントは、WASB ドライバーが提供する Hadoop 分散ファイル システム (HDFS) のインターフェイスを利用して、BLOB として格納された構造化データまたは非構造化データを直接操作できます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-128">Through a Hadoop distributed file system (HDFS) interface provided by a WASB driver, the full set of components in HDInsight can operate directly on structured or unstructured data stored as blobs.</span></span> <span data-ttu-id="fd65c-129">Azure Blob Storage は、PolyBase 機能を使用して Azure SQL Data Warehouse 経由でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-129">Azure Blob storage can also be accessed via Azure SQL Data Warehouse using its PolyBase feature.</span></span>

<span data-ttu-id="fd65c-130">Azure Storage を適切な選択肢にするその他の機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-130">Other features that make Azure Storage a good choice are:</span></span>

- <span data-ttu-id="fd65c-131">[複数の同時実行制御戦略](/azure/storage/common/storage-concurrency?toc=%2fazure%2fstorage%2fblobs%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="fd65c-131">[Multiple concurrency strategies](/azure/storage/common/storage-concurrency?toc=%2fazure%2fstorage%2fblobs%2ftoc.json).</span></span>
- <span data-ttu-id="fd65c-132">[ディザスター リカバリーと高可用性のオプション](/azure/storage/common/storage-disaster-recovery-guidance?toc=%2fazure%2fstorage%2fblobs%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="fd65c-132">[Disaster recovery and high availability options](/azure/storage/common/storage-disaster-recovery-guidance?toc=%2fazure%2fstorage%2fblobs%2ftoc.json).</span></span>
- <span data-ttu-id="fd65c-133">[保存時の暗号化](/azure/storage/common/storage-service-encryption?toc=%2fazure%2fstorage%2fblobs%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="fd65c-133">[Encryption at rest](/azure/storage/common/storage-service-encryption?toc=%2fazure%2fstorage%2fblobs%2ftoc.json).</span></span>
- <span data-ttu-id="fd65c-134">[ロールベースのアクセス制御 (RBAC)](/azure/storage/common/storage-security-guide?toc=%2fazure%2fstorage%2fblobs%2ftoc.json#management-plane-security)。Azure Active Directory のユーザーとグループを使用してアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-134">[Role-Based Access Control (RBAC)](/azure/storage/common/storage-security-guide?toc=%2fazure%2fstorage%2fblobs%2ftoc.json#management-plane-security) to control access using Azure Active Directory users and groups.</span></span>

## <a name="azure-data-lake-store"></a><span data-ttu-id="fd65c-135">Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="fd65c-135">Azure Data Lake Store</span></span>

<span data-ttu-id="fd65c-136">[Azure Data Lake Store](/azure/data-lake-store/) は、ビッグ データの分析ワークロードに対応するエンタープライズ規模のハイパースケール リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="fd65c-136">[Azure Data Lake Store](/azure/data-lake-store/) is an enterprise-wide hyper-scale repository for big data analytic workloads.</span></span> <span data-ttu-id="fd65c-137">Data Lake を使用すると、運用分析や調査分析を目的として任意のサイズ、種類、および取り込み速度のデータを 1 か所の[セキュリティで保護された](/azure/data-lake-store/data-lake-store-overview#DataLakeStoreSecurity)場所にキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-137">Data Lake enables you to capture data of any size, type, and ingestion speed in one single [secure](/azure/data-lake-store/data-lake-store-overview#DataLakeStoreSecurity) location for operational and exploratory analytics.</span></span>

<span data-ttu-id="fd65c-138">Data Lake Store に格納できるアカウント サイズ、ファイル サイズ、またはデータ量に関する制限は設定されていません。</span><span class="sxs-lookup"><span data-stu-id="fd65c-138">Data Lake Store does not impose any limits on account sizes, file sizes, or the amount of data that can be stored in a data lake.</span></span> <span data-ttu-id="fd65c-139">データは複数のコピーを作成して格納されるため、障害が発生しても保護されます。Data Lake でのデータの格納期間に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="fd65c-139">Data is stored durably by making multiple copies and there is no limit on the duration of time that the data can be stored in the Data Lake.</span></span> <span data-ttu-id="fd65c-140">予期しない障害から保護するためのファイルの複数のコピーの作成に加え、Data Lake では、ファイルの一部を、多数の個別のストレージ サーバーに分散させます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-140">In addition to making multiple copies of files to guard against any unexpected failures, Data lake spreads parts of a file over a number of individual storage servers.</span></span> <span data-ttu-id="fd65c-141">これにより、ファイルを並列に読み取ってデータ分析を実行する場合の読み取りスループットが向上します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-141">This improves the read throughput when reading the file in parallel for performing data analytics.</span></span>

<span data-ttu-id="fd65c-142">Data Lake Store には、Hadoop (HDInsight で使用可能) から、WebHDFS 互換の REST API を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-142">Data Lake Store can be accessed from Hadoop (available through HDInsight) using the WebHDFS-compatible REST APIs.</span></span> <span data-ttu-id="fd65c-143">個別のファイルまたは組み合わせたファイルのサイズが Azure Storage でサポートされるファイルのサイズを超える場合は、これを Azure Storage の代わりに使用することを検討できます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-143">You may consider using this as an alternative to Azure Storage when your individual or combined file sizes exceed that which is supported by Azure Storage.</span></span> <span data-ttu-id="fd65c-144">ただし、Data Lake Store を HDInsight クラスターのプライマリ ストレージとして使用する場合に従う必要がある[パフォーマンス チューニング ガイドライン](/azure/data-lake-store/data-lake-store-performance-tuning-guidance#optimizing-io-intensive-jobs-on-hadoop-and-spark-workloads-on-hdinsight)があり、[Spark](/azure/data-lake-store/data-lake-store-performance-tuning-spark)[Hive](/azure/data-lake-store/data-lake-store-performance-tuning-hive)[MapReduce](/azure/data-lake-store/data-lake-store-performance-tuning-mapreduce) および [Storm](/azure/data-lake-store/data-lake-store-performance-tuning-storm) 用の特別なガイドラインがあります。</span><span class="sxs-lookup"><span data-stu-id="fd65c-144">However, there are [performance tuning guidelines](/azure/data-lake-store/data-lake-store-performance-tuning-guidance#optimizing-io-intensive-jobs-on-hadoop-and-spark-workloads-on-hdinsight) you should follow when using Data Lake Store as your primary storage for an HDInsight cluster, with specific guidelines for [Spark](/azure/data-lake-store/data-lake-store-performance-tuning-spark), [Hive](/azure/data-lake-store/data-lake-store-performance-tuning-hive), [MapReduce](/azure/data-lake-store/data-lake-store-performance-tuning-mapreduce), and [Storm](/azure/data-lake-store/data-lake-store-performance-tuning-storm).</span></span> <span data-ttu-id="fd65c-145">また、Data Lake Store の[リージョンでの可用性](https://azure.microsoft.com/regions/#services)を必ず確認してください。それは Azure Storage と同じ数のリージョンでは利用できず、HDInsight クラスターと同じリージョンに配置される必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd65c-145">Also, be sure to check Data Lake Store's [regional availability](https://azure.microsoft.com/regions/#services), because it is not available in as many regions as Azure Storage, and it needs to be located in the same region as your HDInsight cluster.</span></span>

<span data-ttu-id="fd65c-146">Azure Data Lake Analytics と結合された Data Lake Store は、格納されたデータを分析できるように特別に設計されており、データ分析シナリオに合わせてパフォーマンスの調整が行われます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-146">Coupled with Azure Data Lake Analytics, Data Lake Store is specifically designed to enable analytics on the stored data and is tuned for performance for data analytics scenarios.</span></span> <span data-ttu-id="fd65c-147">Data Lake Store は、Azure SQL Data Warehouse の PolyBase 機能を使用してアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-147">Data Lake Store can also be accessed via Azure SQL Data Warehouse using its PolyBase feature.</span></span>

## <a name="azure-cosmos-db"></a><span data-ttu-id="fd65c-148">Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="fd65c-148">Azure Cosmos DB</span></span>

<span data-ttu-id="fd65c-149">[Azure Cosmos DB](/azure/cosmos-db/) は、Microsoft のグローバル分散型マルチモデル データベースです。</span><span class="sxs-lookup"><span data-stu-id="fd65c-149">[Azure Cosmos DB](/azure/cosmos-db/) is Microsoft’s globally distributed multi-model database.</span></span> <span data-ttu-id="fd65c-150">Cosmos DB では、世界中のあらゆる場所で 99 パーセントのユーザーの待機時間が確実に 1 桁ミリ秒となります。また、明確でわかりやすい複数の整合性モデルでパフォーマンスを細かく調整することができ、マルチホーム機能により高可用性も保証されます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-150">Cosmos DB guarantees single-digit-millisecond latencies at the 99th percentile anywhere in the world, offers multiple well-defined consistency models to fine-tune performance, and guarantees high availability with multi-homing capabilities.</span></span>

<span data-ttu-id="fd65c-151">Azure Cosmos DB はスキーマに依存しません。</span><span class="sxs-lookup"><span data-stu-id="fd65c-151">Azure Cosmos DB is schema-agnostic.</span></span> <span data-ttu-id="fd65c-152">それは、全データのインデックスを自動的に作成します。スキーマとインデックスの管理に対処する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fd65c-152">It automatically indexes all the data without requiring you to deal with schema and index management.</span></span> <span data-ttu-id="fd65c-153">またマルチモデルでもあり、ドキュメント、キー値、グラフ、列ファミリのデータ モデルにネイティブに対応しています。</span><span class="sxs-lookup"><span data-stu-id="fd65c-153">It’s also multi-model, natively supporting document, key-value, graph, and column-family data models.</span></span> 

<span data-ttu-id="fd65c-154">Azure Cosmos DB の機能:</span><span class="sxs-lookup"><span data-stu-id="fd65c-154">Azure Cosmos DB features:</span></span>

- [<span data-ttu-id="fd65c-155">geo レプリケーション</span><span class="sxs-lookup"><span data-stu-id="fd65c-155">Geo-replication</span></span>](/azure/cosmos-db/distribute-data-globally)
- <span data-ttu-id="fd65c-156">世界規模での[スループットとストレージのエラスティック スケーリング](/azure/cosmos-db/partition-data)</span><span class="sxs-lookup"><span data-stu-id="fd65c-156">[Elastic scaling of throughput and storage](/azure/cosmos-db/partition-data) worldwide</span></span>
- [<span data-ttu-id="fd65c-157">明確に定義された 5 種類の整合性レベル</span><span class="sxs-lookup"><span data-stu-id="fd65c-157">Five well-defined consistency levels</span></span>](/azure/cosmos-db/consistency-levels)

## <a name="hbase-on-hdinsight"></a><span data-ttu-id="fd65c-158">HDInsight での HBase</span><span class="sxs-lookup"><span data-stu-id="fd65c-158">HBase on HDInsight</span></span>

<span data-ttu-id="fd65c-159">[Apache HBase](http://hbase.apache.org/) は、オープン ソースの NoSQL データベースであり、Hadoop 上に構築され、Google BigTable をモデルにしています。</span><span class="sxs-lookup"><span data-stu-id="fd65c-159">[Apache HBase](http://hbase.apache.org/) is an open-source, NoSQL database that is built on Hadoop and modeled after Google BigTable.</span></span> <span data-ttu-id="fd65c-160">HBase は、大量の非構造化データと半構造化データに対するランダム アクセスと強力な一貫性を、列ファミリで整理されたスキーマなしのデータベースで実現します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-160">HBase provides random access and strong consistency for large amounts of unstructured and semi-structured data in a schemaless database organized by column families.</span></span>

<span data-ttu-id="fd65c-161">データはテーブルの行内に格納され、行内のデータは列ファミリによってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-161">Data is stored in the rows of a table, and data within a row is grouped by column family.</span></span> <span data-ttu-id="fd65c-162">HBase は、列や列内に格納されるデータの型を使用前に定義する必要がないという意味で、スキーマレスです。</span><span class="sxs-lookup"><span data-stu-id="fd65c-162">HBase is schemaless in the sense that neither the columns nor the type of data stored in them need to be defined before using them.</span></span> <span data-ttu-id="fd65c-163">オープン ソース コードは、直線的な拡張により何千ものノード上でペタバイト級のデータを扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-163">The open-source code scales linearly to handle petabytes of data on thousands of nodes.</span></span> <span data-ttu-id="fd65c-164">また、Hadoop エコシステムの分散アプリケーションの利点であるデータの冗長性、バッチ処理などの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-164">It can rely on data redundancy, batch processing, and other features that are provided by distributed applications in the Hadoop ecosystem.</span></span>

<span data-ttu-id="fd65c-165">[HDInsight の実装](/azure/hdinsight/hbase/apache-hbase-overview)と HBase のスケールアウト アーキテクチャにより、テーブルの自動シャーディング、読み取りと書き込みの強力な一貫性、自動フェールオーバーなどが実現します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-165">The [HDInsight implementation](/azure/hdinsight/hbase/apache-hbase-overview) leverages the scale-out architecture of HBase to provide automatic sharding of tables, strong consistency for reads and writes, and automatic failover.</span></span> <span data-ttu-id="fd65c-166">また、メモリ内キャッシュを利用した読み取りと高スループットのストリーミングによる書き込みによって、パフォーマンスも拡張されています。</span><span class="sxs-lookup"><span data-stu-id="fd65c-166">Performance is enhanced by in-memory caching for reads and high-throughput streaming for writes.</span></span> <span data-ttu-id="fd65c-167">ほとんどの場合、[仮想ネットワークの内部に HBase クラスターを作成](/azure/hdinsight/hbase/apache-hbase-provision-vnet)して、他の HDInsight クラスターとアプリケーションがテーブルに直接アクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="fd65c-167">In most cases, you'll want to [create the HBase cluster inside a virtual network](/azure/hdinsight/hbase/apache-hbase-provision-vnet) so other HDInsight clusters and applications can directly access the tables.</span></span>

## <a name="key-selection-criteria"></a><span data-ttu-id="fd65c-168">主要な選択条件</span><span class="sxs-lookup"><span data-stu-id="fd65c-168">Key selection criteria</span></span>

<span data-ttu-id="fd65c-169">選択を絞り込むには、以下の質問に答えることから開始します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-169">To narrow the choices, start by answering these questions:</span></span>

- <span data-ttu-id="fd65c-170">あらゆる種類のテキストまたはバイナリ データ用の管理された高速のクラウド ベースのストレージが必要か。</span><span class="sxs-lookup"><span data-stu-id="fd65c-170">Do you need managed, high speed, cloud-based storage for any type of text or binary data?</span></span> <span data-ttu-id="fd65c-171">必要な場合は、ファイル ストレージ オプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-171">If yes, then select one of the file storage options.</span></span>

- <span data-ttu-id="fd65c-172">並列分析ワークロードと高いスループット/IOPS 用に最適化されたファイル ストレージが必要か。</span><span class="sxs-lookup"><span data-stu-id="fd65c-172">Do you need file storage that is optimized for parallel analytics workloads and high throughput/IOPS?</span></span> <span data-ttu-id="fd65c-173">必要な場合は、分析ワークロードのパフォーマンスを調整するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-173">If yes, then choose an option that is tuned to analytics workload performance.</span></span>

- <span data-ttu-id="fd65c-174">Schemaless データベースで非構造化または半構造化データを格納する必要があるか。</span><span class="sxs-lookup"><span data-stu-id="fd65c-174">Do you need to store unstructured or semi-structured data in a schemaless database?</span></span> <span data-ttu-id="fd65c-175">ある場合は、非リレーショナル オプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-175">If so, select one of the non-relational options.</span></span> <span data-ttu-id="fd65c-176">インデックス作成とデータベース モデルのオプションを比較します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-176">Compare options for indexing and database models.</span></span> <span data-ttu-id="fd65c-177">格納する必要があるデータの種類によっては、プライマリ データベース モデルが最大の要素になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fd65c-177">Depending on the type of data you need to store, the primary database models may be the largest factor.</span></span>

- <span data-ttu-id="fd65c-178">在住しているリージョンでサービスを利用できるか。</span><span class="sxs-lookup"><span data-stu-id="fd65c-178">Can you use the service in your region?</span></span> <span data-ttu-id="fd65c-179">各 Azure サービスの利用可能リージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-179">Check the regional availability for each Azure service.</span></span> <span data-ttu-id="fd65c-180">「[リージョン別の利用可能な製品](https://azure.microsoft.com/regions/services/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd65c-180">See [Products available by region](https://azure.microsoft.com/regions/services/).</span></span>

## <a name="capability-matrix"></a><span data-ttu-id="fd65c-181">機能のマトリックス</span><span class="sxs-lookup"><span data-stu-id="fd65c-181">Capability matrix</span></span>

<span data-ttu-id="fd65c-182">次の表は、機能の主な相違点をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="fd65c-182">The following tables summarize the key differences in capabilities.</span></span>

### <a name="file-storage-capabilities"></a><span data-ttu-id="fd65c-183">File Storage の機能</span><span class="sxs-lookup"><span data-stu-id="fd65c-183">File storage capabilities</span></span>

|  | <span data-ttu-id="fd65c-184">Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="fd65c-184">Azure Data Lake Store</span></span> | <span data-ttu-id="fd65c-185">Azure Blob Storage コンテナー</span><span class="sxs-lookup"><span data-stu-id="fd65c-185">Azure Blob Storage containers</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fd65c-186">目的</span><span class="sxs-lookup"><span data-stu-id="fd65c-186">Purpose</span></span> | <span data-ttu-id="fd65c-187">ビッグ データ分析ワークロードに最適化されたストレージ</span><span class="sxs-lookup"><span data-stu-id="fd65c-187">Optimized storage for big data analytics workloads</span></span> |<span data-ttu-id="fd65c-188">さまざまなストレージ シナリオに対応する汎用オブジェクト ストア</span><span class="sxs-lookup"><span data-stu-id="fd65c-188">General purpose object store for a wide variety of storage scenarios</span></span> |
| <span data-ttu-id="fd65c-189">ユース ケース</span><span class="sxs-lookup"><span data-stu-id="fd65c-189">Use cases</span></span> | <span data-ttu-id="fd65c-190">バッチ、ストリーミング分析、および機械学習データ (ログ ファイル、IoT データ、クリック ストリーム、大規模なデータセットなど)</span><span class="sxs-lookup"><span data-stu-id="fd65c-190">Batch, streaming analytics, and machine learning data such as log files, IoT data, click streams, large datasets</span></span> | <span data-ttu-id="fd65c-191">あらゆる種類のテキスト データまたはバイナリ データ (アプリケーション バックエンド、バックアップ データ、ストリーミング用メディア ストレージ、汎用データなど)</span><span class="sxs-lookup"><span data-stu-id="fd65c-191">Any type of text or binary data, such as application back end, backup data, media storage for streaming, and general purpose data</span></span> |
| <span data-ttu-id="fd65c-192">Structure</span><span class="sxs-lookup"><span data-stu-id="fd65c-192">Structure</span></span> | <span data-ttu-id="fd65c-193">階層型ファイル システム</span><span class="sxs-lookup"><span data-stu-id="fd65c-193">Hierarchical file system</span></span> | <span data-ttu-id="fd65c-194">フラットな名前空間を使用するオブジェクト ストア</span><span class="sxs-lookup"><span data-stu-id="fd65c-194">Object store with flat namespace</span></span> |
| <span data-ttu-id="fd65c-195">認証</span><span class="sxs-lookup"><span data-stu-id="fd65c-195">Authentication</span></span> | <span data-ttu-id="fd65c-196">[Azure Active Directory ID](/azure/active-directory/active-directory-authentication-scenarios)</span><span class="sxs-lookup"><span data-stu-id="fd65c-196">Based on [Azure Active Directory Identities](/azure/active-directory/active-directory-authentication-scenarios)</span></span> | <span data-ttu-id="fd65c-197">共有シークレット ([アカウント アクセス キー](/azure/storage/common/storage-create-storage-account#manage-your-storage-account)と [Shared Access Signature キー)](/azure/storage/common/storage-dotnet-shared-access-signature-part-1)、および[ロールベースのアクセス制御 (RBAC)](/azure/security/security-storage-overview) に基づく</span><span class="sxs-lookup"><span data-stu-id="fd65c-197">Based on shared secrets [Account Access Keys](/azure/storage/common/storage-create-storage-account#manage-your-storage-account) and [Shared Access Signature Keys](/azure/storage/common/storage-dotnet-shared-access-signature-part-1), and [Role-Based Access Control (RBAC)](/azure/security/security-storage-overview)</span></span> |
| <span data-ttu-id="fd65c-198">認証プロトコル</span><span class="sxs-lookup"><span data-stu-id="fd65c-198">Authentication protocol</span></span> | <span data-ttu-id="fd65c-199">OAuth 2.0。</span><span class="sxs-lookup"><span data-stu-id="fd65c-199">OAuth 2.0.</span></span> <span data-ttu-id="fd65c-200">呼び出しには、Azure Active Directory によって発行された有効な JWT (JSON Web トークン) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd65c-200">Calls must contain a valid JWT (JSON web token) issued by Azure Active Directory</span></span> | <span data-ttu-id="fd65c-201">ハッシュベース メッセージ認証コード (HMAC)。</span><span class="sxs-lookup"><span data-stu-id="fd65c-201">Hash-based message authentication code (HMAC).</span></span> <span data-ttu-id="fd65c-202">呼び出しには、HTTP 要求の一部に対する Base64 でエンコードされた SHA-256 ハッシュが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd65c-202">Calls must contain a Base64-encoded SHA-256 hash over a part of the HTTP request.</span></span> |
| <span data-ttu-id="fd65c-203">承認</span><span class="sxs-lookup"><span data-stu-id="fd65c-203">Authorization</span></span> | <span data-ttu-id="fd65c-204">POSIX アクセス制御リスト (ACL)。</span><span class="sxs-lookup"><span data-stu-id="fd65c-204">POSIX access control lists (ACLs).</span></span> <span data-ttu-id="fd65c-205">Azure Active Directory ID に基づく ACL は、ファイルおよびフォルダー レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="fd65c-205">ACLs based on Azure Active Directory identities can be set file and folder level.</span></span> | <span data-ttu-id="fd65c-206">アカウントレベルの承認には、[アカウント アクセス キー](/azure/storage/common/storage-create-storage-account#manage-your-storage-account)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-206">For account-level authorization use [Account Access Keys](/azure/storage/common/storage-create-storage-account#manage-your-storage-account).</span></span> <span data-ttu-id="fd65c-207">アカウント、コンテナー、または BLOB の承認には、[Shared Access Signature キー](/azure/storage/common/storage-dotnet-shared-access-signature-part-1)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd65c-207">For account, container, or blob authorization use [Shared Access Signature Keys](/azure/storage/common/storage-dotnet-shared-access-signature-part-1).</span></span> |
| <span data-ttu-id="fd65c-208">監査</span><span class="sxs-lookup"><span data-stu-id="fd65c-208">Auditing</span></span> | <span data-ttu-id="fd65c-209">使用可能。</span><span class="sxs-lookup"><span data-stu-id="fd65c-209">Available.</span></span>  |<span data-ttu-id="fd65c-210">使用可能</span><span class="sxs-lookup"><span data-stu-id="fd65c-210">Available</span></span> |
| <span data-ttu-id="fd65c-211">保存時の暗号化</span><span class="sxs-lookup"><span data-stu-id="fd65c-211">Encryption at rest</span></span> | <span data-ttu-id="fd65c-212">透過的、サーバー側</span><span class="sxs-lookup"><span data-stu-id="fd65c-212">Transparent, server side</span></span> | <span data-ttu-id="fd65c-213">透過、サーバー側。クライアント側の暗号化</span><span class="sxs-lookup"><span data-stu-id="fd65c-213">Transparent, server side; Client-side encryption</span></span> |
| <span data-ttu-id="fd65c-214">Developer SDK</span><span class="sxs-lookup"><span data-stu-id="fd65c-214">Developer SDKs</span></span> | <span data-ttu-id="fd65c-215">.NET、Java、Python、Node.js</span><span class="sxs-lookup"><span data-stu-id="fd65c-215">.NET, Java, Python, Node.js</span></span> | <span data-ttu-id="fd65c-216">.Net、Java、Python、Node.js、C++、Ruby</span><span class="sxs-lookup"><span data-stu-id="fd65c-216">.Net, Java, Python, Node.js, C++, Ruby</span></span> |
| <span data-ttu-id="fd65c-217">分析ワークロードのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="fd65c-217">Analytics workload performance</span></span> | <span data-ttu-id="fd65c-218">並列分析ワークロードに最適化されたパフォーマンス。高いスループットと IOPS</span><span class="sxs-lookup"><span data-stu-id="fd65c-218">Optimized performance for parallel analytics workloads, High Throughput and IOPS</span></span> | <span data-ttu-id="fd65c-219">分析ワークロードに最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="fd65c-219">Not optimized for analytics workloads</span></span> |
| <span data-ttu-id="fd65c-220">サイズ制限</span><span class="sxs-lookup"><span data-stu-id="fd65c-220">Size limits</span></span> | <span data-ttu-id="fd65c-221">アカウント サイズ、ファイル サイズ、ファイル数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="fd65c-221">No limits on account sizes, file sizes or number of files</span></span> | <span data-ttu-id="fd65c-222">具体的な制限については、 [こちら](/azure/azure-subscription-service-limits#storage-limits)</span><span class="sxs-lookup"><span data-stu-id="fd65c-222">Specific limits documented [here](/azure/azure-subscription-service-limits#storage-limits)</span></span> |
| <span data-ttu-id="fd65c-223">geo 冗長</span><span class="sxs-lookup"><span data-stu-id="fd65c-223">Geo-redundancy</span></span> | <span data-ttu-id="fd65c-224">ローカル冗長 (1 つの Azure リージョンにデータの複数のコピー)</span><span class="sxs-lookup"><span data-stu-id="fd65c-224">Locally-redundant (multiple copies of data in one Azure region)</span></span> | <span data-ttu-id="fd65c-225">ローカル冗長 (LRS)、geo 冗長 (GRS)、読み取りアクセス geo 冗長 (RA-GRS)。</span><span class="sxs-lookup"><span data-stu-id="fd65c-225">Locally redundant (LRS), globally redundant (GRS), read-access globally redundant (RA-GRS).</span></span> <span data-ttu-id="fd65c-226">詳細については、 [こちら](/azure/storage/common/storage-redundancy) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fd65c-226">See [here](/azure/storage/common/storage-redundancy) for more information</span></span> |

### <a name="nosql-database-capabilities"></a><span data-ttu-id="fd65c-227">NoSQL データベースの機能</span><span class="sxs-lookup"><span data-stu-id="fd65c-227">NoSQL database capabilities</span></span>

| | <span data-ttu-id="fd65c-228">Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="fd65c-228">Azure Cosmos DB</span></span> | <span data-ttu-id="fd65c-229">HDInsight での HBase</span><span class="sxs-lookup"><span data-stu-id="fd65c-229">HBase on HDInsight</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fd65c-230">プライマリ データベース モデル</span><span class="sxs-lookup"><span data-stu-id="fd65c-230">Primary database model</span></span> | <span data-ttu-id="fd65c-231">ドキュメント ストア、グラフ、キー値ストア、ワイド カラム ストア</span><span class="sxs-lookup"><span data-stu-id="fd65c-231">Document store, graph, key-value store, wide column store</span></span> | <span data-ttu-id="fd65c-232">ワイド カラム ストア</span><span class="sxs-lookup"><span data-stu-id="fd65c-232">Wide column store</span></span> |
| <span data-ttu-id="fd65c-233">セカンダリ インデックス</span><span class="sxs-lookup"><span data-stu-id="fd65c-233">Secondary indexes</span></span> | <span data-ttu-id="fd65c-234">[はい]</span><span class="sxs-lookup"><span data-stu-id="fd65c-234">Yes</span></span> | <span data-ttu-id="fd65c-235">いいえ </span><span class="sxs-lookup"><span data-stu-id="fd65c-235">No</span></span> |
| <span data-ttu-id="fd65c-236">SQL 言語のサポート</span><span class="sxs-lookup"><span data-stu-id="fd65c-236">SQL language support</span></span> | <span data-ttu-id="fd65c-237">[はい]</span><span class="sxs-lookup"><span data-stu-id="fd65c-237">Yes</span></span> | <span data-ttu-id="fd65c-238">はい ([Phoenix](http://phoenix.apache.org/) JDBC ドライバーを使用)</span><span class="sxs-lookup"><span data-stu-id="fd65c-238">Yes (using the [Phoenix](http://phoenix.apache.org/) JDBC driver)</span></span> |
| <span data-ttu-id="fd65c-239">整合性</span><span class="sxs-lookup"><span data-stu-id="fd65c-239">Consistency</span></span> | <span data-ttu-id="fd65c-240">強固、有界整合性制約、セッション、一貫性のあるプレフィックス、最終的</span><span class="sxs-lookup"><span data-stu-id="fd65c-240">Strong, bounded-staleness, session, consistent prefix, eventual</span></span> | <span data-ttu-id="fd65c-241">Strong</span><span class="sxs-lookup"><span data-stu-id="fd65c-241">Strong</span></span> |
| <span data-ttu-id="fd65c-242">Azure Functions のネイティブ統合</span><span class="sxs-lookup"><span data-stu-id="fd65c-242">Native Azure Functions integration</span></span> | [<span data-ttu-id="fd65c-243">はい</span><span class="sxs-lookup"><span data-stu-id="fd65c-243">Yes</span></span>](/azure/cosmos-db/serverless-computing-database) | <span data-ttu-id="fd65c-244">いいえ </span><span class="sxs-lookup"><span data-stu-id="fd65c-244">No</span></span> |
| <span data-ttu-id="fd65c-245">自動的なグローバル分散</span><span class="sxs-lookup"><span data-stu-id="fd65c-245">Automatic global distribution</span></span> | [<span data-ttu-id="fd65c-246">はい</span><span class="sxs-lookup"><span data-stu-id="fd65c-246">Yes</span></span>](/azure/cosmos-db/distribute-data-globally) | <span data-ttu-id="fd65c-247">いいえ。最終的な整合性を指定して、リージョン間で[HBase クラスターのレプリケーションを構成可能](/azure/hdinsight/hbase/apache-hbase-replication)</span><span class="sxs-lookup"><span data-stu-id="fd65c-247">No [HBase cluster replication can be configured](/azure/hdinsight/hbase/apache-hbase-replication) across regions with eventual consistency</span></span> |
| <span data-ttu-id="fd65c-248">価格モデル</span><span class="sxs-lookup"><span data-stu-id="fd65c-248">Pricing model</span></span> | <span data-ttu-id="fd65c-249">必要に応じて秒単位で課金され、弾力的にスケーラブルな要求ユニット (RU)。弾力的にスケーラブルなストレージ</span><span class="sxs-lookup"><span data-stu-id="fd65c-249">Elastically scalable request units (RUs) charged per-second as needed, elastically scalable storage</span></span> | <span data-ttu-id="fd65c-250">HDInsight クラスターの分単位の料金 (ノードの水平スケーリング)、ストレージ</span><span class="sxs-lookup"><span data-stu-id="fd65c-250">Per-minute pricing for HDInsight cluster (horizontal scaling of nodes), storage</span></span> |