---
title: Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET
description: Descargar las bases de datos de ejemplo utilizados en los ejemplos de código en la documentación de ADO.NET, así como herramientas de administración y SQL Server
ms.date: 10/12/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 75ae1895d683b669f51b33130fc2f47010e39814
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347532"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="c17bb-103">Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c17bb-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="c17bb-104">Un número de ejemplos y tutoriales en la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación usar bases de datos y SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="c17bb-104">A number of samples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample databases and SQL Server Express.</span></span> <span data-ttu-id="c17bb-105">Puede descargar estos productos de forma gratuita de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c17bb-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-adventureworks-sample-database"></a><span data-ttu-id="c17bb-106">Obtener la base de datos de ejemplo AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="c17bb-106">Get the AdventureWorks sample database</span></span>

<span data-ttu-id="c17bb-107">Descargue la base de datos de ejemplo AdventureWorks desde el repositorio de GitHub siguiente:</span><span class="sxs-lookup"><span data-stu-id="c17bb-107">Download the AdventureWorks sample database from the following GitHub repository:</span></span>

[<span data-ttu-id="c17bb-108">Bases de datos de ejemplo de AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="c17bb-108">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="c17bb-109">Después de descargar uno de la copia de seguridad de base de datos (\*.bak) de los archivos, restaurar la copia de seguridad a una instancia de SQL Server mediante SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="c17bb-109">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="c17bb-110">Consulte [tener SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="c17bb-110">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-the-northwind-sample-database"></a><span data-ttu-id="c17bb-111">Obtener la base de datos de ejemplo Northwind</span><span class="sxs-lookup"><span data-stu-id="c17bb-111">Get the Northwind sample database</span></span>

<span data-ttu-id="c17bb-112">Descargue la base de datos de ejemplo Northwind desde la página siguiente en Microsoft Download Center:</span><span class="sxs-lookup"><span data-stu-id="c17bb-112">Download the Northwind sample database from the following page in the Microsoft Download Center:</span></span>

[<span data-ttu-id="c17bb-113">Bases de datos de ejemplo Pubs y Northwind</span><span class="sxs-lookup"><span data-stu-id="c17bb-113">Northwind and Pubs Sample Databases</span></span>](https://go.microsoft.com/fwlink?linkid=64296)

<span data-ttu-id="c17bb-114">Una vez descargado el archivo, haga doble clic en el archivo para extraer las bases de datos y los scripts.</span><span class="sxs-lookup"><span data-stu-id="c17bb-114">After the file has downloaded, double-click the file to extract the databases and scripts.</span></span> <span data-ttu-id="c17bb-115">De forma predeterminada, los archivos se instalan en la carpeta `<drive>:\SQL Server 2000 Sample Databases`.</span><span class="sxs-lookup"><span data-stu-id="c17bb-115">By default, the files are installed in the folder `<drive>:\SQL Server 2000 Sample Databases`.</span></span>

<span data-ttu-id="c17bb-116">Para poder usar la base de datos Northwind, que debe hacer una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c17bb-116">Before you can use the Northwind database, you have to do one of the following things:</span></span>

- <span data-ttu-id="c17bb-117">Volver a crear la base de datos en una instancia de SQL Server ejecutando el `instnwnd.sql` archivo de script en la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="c17bb-117">Recreate the database on an instance of SQL Server by running the `instnwnd.sql` script file in the installation folder.</span></span>

- <span data-ttu-id="c17bb-118">Adjuntar el `northwnd.mdf` archivo con sus correspondientes `*.ldf` archivo de registro a una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c17bb-118">Attach the `northwnd.mdf` file with its corresponding `*.ldf` log file to an instance of SQL Server.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="c17bb-119">Obtener SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="c17bb-119">Get SQL Server Express</span></span>

<span data-ttu-id="c17bb-120">SQL Server Express es una edición gratuita, nivel de entrada de SQL Server que se puede redistribuir con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c17bb-120">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="c17bb-121">Descargar SQL Server Express desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="c17bb-121">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="c17bb-122">Ediciones de SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="c17bb-122">SQL Server Express Editions</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="c17bb-123">Si usas [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB se incluye en la edición Community, así como las ediciones Professional y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c17bb-123">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the Community edition as well as the Professional and higher editions.</span></span>  

## <a name="get_ssms"></a> <span data-ttu-id="c17bb-124">Obtener SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c17bb-124">Get SQL Server Management Studio</span></span>
<span data-ttu-id="c17bb-125">Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="c17bb-125">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="c17bb-126">Descarga de SSMS desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="c17bb-126">Download SSMS from the following page:</span></span>

[<span data-ttu-id="c17bb-127">Descargar SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="c17bb-127">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="c17bb-128">También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c17bb-128">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="c17bb-129">En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), conectarse a la base de datos **Explorador de objetos de SQL Server**, o crear una conexión de datos a la base de datos en **Explorador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="c17bb-129">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="c17bb-130">Abrir estos paneles explorador desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="c17bb-130">Open these explorer panes from the **View** menu.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c17bb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c17bb-131">See also</span></span>

- [<span data-ttu-id="c17bb-132">Introducción</span><span class="sxs-lookup"><span data-stu-id="c17bb-132">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
