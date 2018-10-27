---
title: Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET
description: Descargar las bases de datos de ejemplo utilizados en los ejemplos de código en la documentación de ADO.NET, así como herramientas de administración y SQL Server
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 9779300288135cb9332a028d547ce55a07e89471
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188396"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="93ec7-103">Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET</span><span class="sxs-lookup"><span data-stu-id="93ec7-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="93ec7-104">Un número de ejemplos y tutoriales en la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación usar bases de datos y SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="93ec7-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="93ec7-105">Puede descargar estos productos de forma gratuita de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93ec7-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="93ec7-106">Obtener la base de datos de ejemplo Northwind</span><span class="sxs-lookup"><span data-stu-id="93ec7-106">Get the Northwind sample database</span></span>

<span data-ttu-id="93ec7-107">Descargue la base de datos de ejemplo Northwind desde la página siguiente en Microsoft Download Center:</span><span class="sxs-lookup"><span data-stu-id="93ec7-107">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="93ec7-108">Bases de datos de ejemplo Pubs y Northwind</span><span class="sxs-lookup"><span data-stu-id="93ec7-108">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="93ec7-109">Una vez descargado el archivo, haga doble clic en el archivo para extraer las bases de datos y los scripts.</span><span class="sxs-lookup"><span data-stu-id="93ec7-109">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="93ec7-110">De forma predeterminada, los archivos se instalan en la carpeta `<drive>:\SQL Server 2000 Sample Databases`.</span><span class="sxs-lookup"><span data-stu-id="93ec7-110">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="93ec7-111">Para poder usar la base de datos Northwind, tendrá que volver a crear la base de datos en una instancia de SQL Server mediante el uso de [SQL Server Management Studio](#get_ssms) u otra herramienta similar para ejecutar el `instnwnd.sql` archivo de script en la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="93ec7-111">Before you can use the Northwind database, you have to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool to run the `instnwnd.sql` script file in the installation folder.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="93ec7-112">Obtener la base de datos de ejemplo AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="93ec7-112">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="93ec7-113">Descargue la base de datos de ejemplo AdventureWorks desde el repositorio de GitHub siguiente:</span><span class="sxs-lookup"><span data-stu-id="93ec7-113">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="93ec7-114">Bases de datos de ejemplo de AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="93ec7-114">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="93ec7-115">Después de descargar uno de la copia de seguridad de base de datos (\*.bak) de los archivos, restaurar la copia de seguridad a una instancia de SQL Server mediante SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="93ec7-115">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="93ec7-116">Consulte [tener SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="93ec7-116">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_sql"></a> <span data-ttu-id="93ec7-117">Obtener SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="93ec7-117">Get SQL Server Express</span></span>

<span data-ttu-id="93ec7-118">SQL Server Express es una edición gratuita, nivel de entrada de SQL Server que se puede redistribuir con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="93ec7-118">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="93ec7-119">Descargar SQL Server Express desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="93ec7-119">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="93ec7-120">Ediciones de SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="93ec7-120">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="93ec7-121">Si usas [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB se incluye en la edición gratuita Community, así como las ediciones Professional y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="93ec7-121">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="93ec7-122">Obtener SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93ec7-122">Get SQL Server Management Studio</span></span>
<span data-ttu-id="93ec7-123">Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="93ec7-123">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="93ec7-124">Descarga de SSMS desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="93ec7-124">Download SSMS from the following page:</span></span>

[<span data-ttu-id="93ec7-125">Descargar SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="93ec7-125">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="93ec7-126">También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93ec7-126">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="93ec7-127">En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), conectarse a la base de datos **Explorador de objetos de SQL Server**, o crear una conexión de datos a la base de datos en **Explorador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="93ec7-127">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="93ec7-128">Abrir estos paneles explorador desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="93ec7-128">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93ec7-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="93ec7-129">See also</span></span>

- [<span data-ttu-id="93ec7-130">Introducción</span><span class="sxs-lookup"><span data-stu-id="93ec7-130">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
