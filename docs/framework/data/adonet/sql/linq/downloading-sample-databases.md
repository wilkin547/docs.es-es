---
title: Obtener las bases de datos de SQL Server de ejemplo para obtener ejemplos de código ADO.NET
description: Descargar las bases de datos de SQL Server de ejemplo utilizados en los ejemplos de código en la documentación de ADO.NET, así como herramientas de administración y SQL Server
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 5580f06f3d28ed6d70f75b619498ac8de7bc3326
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307297"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="bf5d0-103">Obtener las bases de datos de ejemplo para obtener ejemplos de código ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bf5d0-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="bf5d0-104">Un número de ejemplos y tutoriales en la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación usar bases de datos de ejemplo SQL Server y SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="bf5d0-105">Puede descargar estos productos de forma gratuita de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="bf5d0-106">Obtenga la base de datos de ejemplo Northwind para SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf5d0-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="bf5d0-107">Descargue el script `instnwnd.sql` desde el repositorio de GitHub siguiente para crear y cargar la base de datos de ejemplo Northwind para SQL Server:</span><span class="sxs-lookup"><span data-stu-id="bf5d0-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="bf5d0-108">Northwind y pubs bases de datos de ejemplo para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf5d0-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="bf5d0-109">Para poder usar la base de datos Northwind, tendrá que ejecutar los datos descargados `instnwnd.sql` archivo de script para volver a crear la base de datos en una instancia de SQL Server mediante el uso de [SQL Server Management Studio](#get_ssms) u otra herramienta similar.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="bf5d0-110">Siga las instrucciones del archivo Léame del repositorio.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="bf5d0-111">Si busca la base de datos Northwind para Microsoft Access, consulte [instalar la base de datos de ejemplo Northwind para Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="bf5d0-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="northwind_access"></a> <span data-ttu-id="bf5d0-112">Obtener la base de datos de ejemplo Northwind para Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="bf5d0-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="bf5d0-113">La base de datos de ejemplo Northwind para Microsoft Access no está disponible en Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="bf5d0-114">Para instalar Northwind directamente desde dentro de acceso, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf5d0-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="bf5d0-115">Abre el acceso.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-115">Open Access.</span></span>

1. <span data-ttu-id="bf5d0-116">ENTRAR **Northwind** en el **buscar plantillas en línea** cuadro y, a continuación, seleccione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="bf5d0-117">En la pantalla de resultados, seleccione **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="bf5d0-118">Se abre una nueva ventana con una descripción de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="bf5d0-119">En la ventana nueva, en el **nombre de archivo** texto cuadro, proporcione un nombre de archivo para su copia de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="bf5d0-120">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-120">Select **Create**.</span></span> <span data-ttu-id="bf5d0-121">Acceso a descargas de la base de datos Northwind y prepara el archivo.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="bf5d0-122">Una vez completado este proceso, se abre la base de datos con una pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="bf5d0-123">Obtenga la base de datos de ejemplo AdventureWorks para SQL Server</span><span class="sxs-lookup"><span data-stu-id="bf5d0-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="bf5d0-124">Descargue la base de datos de ejemplo AdventureWorks para SQL Server desde el repositorio de GitHub siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf5d0-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="bf5d0-125">Bases de datos de ejemplo de AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="bf5d0-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="bf5d0-126">Después de descargar uno de la copia de seguridad de base de datos (\*.bak) de los archivos, restaurar la copia de seguridad a una instancia de SQL Server mediante SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="bf5d0-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="bf5d0-127">Consulte [tener SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="bf5d0-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_ssms"></a> <span data-ttu-id="bf5d0-128">Obtener SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bf5d0-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="bf5d0-129">Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="bf5d0-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="bf5d0-130">Descarga de SSMS desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf5d0-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="bf5d0-131">Descargar SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="bf5d0-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="bf5d0-132">También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="bf5d0-133">En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), conectarse a la base de datos **Explorador de objetos de SQL Server**, o crear una conexión de datos a la base de datos en **Explorador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="bf5d0-134">Abrir estos paneles explorador desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="bf5d0-135">Obtener SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="bf5d0-135">Get SQL Server Express</span></span>

<span data-ttu-id="bf5d0-136">SQL Server Express es una edición gratuita, nivel de entrada de SQL Server que se puede redistribuir con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="bf5d0-137">Descargar SQL Server Express desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf5d0-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="bf5d0-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="bf5d0-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="bf5d0-139">Si usas [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB se incluye en la edición gratuita Community de Visual Studio, así como las ediciones Professional y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="bf5d0-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="bf5d0-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf5d0-140">See also</span></span>

- [<span data-ttu-id="bf5d0-141">Introducción</span><span class="sxs-lookup"><span data-stu-id="bf5d0-141">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
