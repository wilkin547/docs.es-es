---
title: Obtener las bases de datos de ejemplo SQL Server para ejemplos de código de ADO.NET
description: Descargue las bases de datos de SQL Server de ejemplo usadas en los ejemplos de código de la documentación de ADO.NET, así como herramientas de SQL Server y administración
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: f7c0d1eb0089a6bfabc92e1deecf563c3e59cc6a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156061"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="b9ee6-103">Obtener las bases de datos de ejemplo para los ejemplos de código de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9ee6-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="b9ee6-104">Una serie de ejemplos y tutoriales en la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación de utilizan bases de datos de ejemplo SQL Server y SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="b9ee6-105">Puede descargar estos productos de forma gratuita de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="b9ee6-106">Obtener la base de datos de ejemplo Northwind para SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9ee6-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="b9ee6-107">Descargue el script `instnwnd.sql` desde el siguiente repositorio de github para crear y cargar la base de datos de ejemplo Northwind para SQL Server:</span><span class="sxs-lookup"><span data-stu-id="b9ee6-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="b9ee6-108">Bases de datos de ejemplo Northwind y pubs para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9ee6-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="b9ee6-109">Antes de poder usar la base de datos Northwind, tiene que ejecutar el archivo de script descargado `instnwnd.sql` para volver a crear la base de datos en una instancia de SQL Server mediante [SQL Server Management Studio](#get_ssms) u otra herramienta similar.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="b9ee6-110">Siga las instrucciones del archivo Léame del repositorio.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="b9ee6-111">Si está buscando la base de datos Northwind para Microsoft Access, vea [instalar la base de datos de ejemplo Northwind para Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="b9ee6-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a> <span data-ttu-id="b9ee6-112">Obtención de la base de datos de ejemplo Northwind para Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="b9ee6-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="b9ee6-113">La base de datos de ejemplo Northwind para Microsoft Access no está disponible en el centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="b9ee6-114">Para instalar Northwind directamente desde el acceso, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9ee6-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="b9ee6-115">Abra el acceso.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-115">Open Access.</span></span>

1. <span data-ttu-id="b9ee6-116">Escriba **Northwind** en el cuadro **buscar plantillas en línea** y, a continuación, seleccione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="b9ee6-117">En la pantalla resultados, seleccione **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="b9ee6-118">Se abre una nueva ventana con una descripción de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="b9ee6-119">En la nueva ventana, en el cuadro de texto **nombre de archivo** , proporcione un nombre de archivo para la copia de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="b9ee6-120">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-120">Select **Create**.</span></span> <span data-ttu-id="b9ee6-121">Access descarga la base de datos Northwind y prepara el archivo.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="b9ee6-122">Una vez completado este proceso, la base de datos se abre con una pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="b9ee6-123">Obtener la base de datos de ejemplo AdventureWorks para SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9ee6-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="b9ee6-124">Descargue la base de datos de ejemplo AdventureWorks para SQL Server desde el siguiente repositorio de GitHub:</span><span class="sxs-lookup"><span data-stu-id="b9ee6-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="b9ee6-125">Bases de datos de ejemplo AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="b9ee6-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="b9ee6-126">Después de descargar uno de los archivos de copia de seguridad de base de datos ( \* . bak), restaure la copia de seguridad en una instancia de SQL Server mediante SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="b9ee6-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="b9ee6-127">Vea [obtener SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="b9ee6-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a> <span data-ttu-id="b9ee6-128">Obtener SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9ee6-128">Get SQL Server Management Studio</span></span>

<span data-ttu-id="b9ee6-129">Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="b9ee6-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="b9ee6-130">Descargue SSMS en la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9ee6-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="b9ee6-131">Descarga de SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="b9ee6-132">También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="b9ee6-133">En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), conéctese a la base de datos desde **Explorador de objetos de SQL Server**, o cree una conexión de datos a la base de datos en **Explorador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="b9ee6-134">Abra estos paneles del explorador en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="b9ee6-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a> <span data-ttu-id="b9ee6-135">Obtener SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="b9ee6-135">Get SQL Server Express</span></span>

<span data-ttu-id="b9ee6-136">SQL Server Express es una edición gratuita de nivel de entrada de SQL Server que se puede redistribuir con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="b9ee6-137">Descargue SQL Server Express de la siguiente página:</span><span class="sxs-lookup"><span data-stu-id="b9ee6-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="b9ee6-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="b9ee6-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="b9ee6-139">Si utiliza [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB se incluye en la edición gratuita Community de Visual Studio, así como en las ediciones Professional y superior.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b9ee6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9ee6-140">See also</span></span>

- [<span data-ttu-id="b9ee6-141">Introducción</span><span class="sxs-lookup"><span data-stu-id="b9ee6-141">Getting Started</span></span>](getting-started.md)
