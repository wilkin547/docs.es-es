---
title: Obtenga las bases de datos de SQL Server de ejemplo para ADO.NET ejemplos de código
description: Descargue las bases de datos de SQL Server de ejemplo utilizadas en los ejemplos de código de la documentación de ADO.NET, así como SQL Server y las herramientas de administración
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 3449f502834f449f5023bd52457d45ffaf9b0fa1
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607989"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="a509e-103">Obtenga las bases de datos de ejemplo para ejemplos de código ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a509e-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="a509e-104">Varios ejemplos y tutoriales [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de la documentación usan bases de datos de SQL Server de ejemplo y SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a509e-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="a509e-105">Puede descargar estos productos de forma gratuita desde Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a509e-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="a509e-106">Obtenga la base de datos de ejemplo Northwind para SQL Server</span><span class="sxs-lookup"><span data-stu-id="a509e-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="a509e-107">Descargue el `instnwnd.sql` script del siguiente repositorio GitHub para crear y cargar la base de datos de ejemplo Northwind para SQL Server:</span><span class="sxs-lookup"><span data-stu-id="a509e-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="a509e-108">Bases de datos de ejemplo Northwind y pubs para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a509e-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="a509e-109">Para poder usar la base de datos Northwind, debe ejecutar el archivo de script descargado `instnwnd.sql` para volver a crear la base de datos en una instancia de SQL Server mediante SQL Server Management [StudioSQL Server Management Studio](#get_ssms) o una herramienta similar.</span><span class="sxs-lookup"><span data-stu-id="a509e-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="a509e-110">Siga las instrucciones del archivo Léame del repositorio.</span><span class="sxs-lookup"><span data-stu-id="a509e-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="a509e-111">Si está buscando la base de datos Northwind para Microsoft Access, consulte Instalar la base de datos de [ejemplo Northwind para Microsoft Access](#northwind_access).</span><span class="sxs-lookup"><span data-stu-id="a509e-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a><span data-ttu-id="a509e-112">Obtenga la base de datos de ejemplo Northwind para Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="a509e-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="a509e-113">La base de datos de ejemplo Northwind para Microsoft Access no está disponible en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a509e-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="a509e-114">Para instalar Northwind directamente desde Access, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a509e-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="a509e-115">Abra Acceso.</span><span class="sxs-lookup"><span data-stu-id="a509e-115">Open Access.</span></span>

1. <span data-ttu-id="a509e-116">Escriba **Northwind** en el cuadro **Buscar plantillas en línea** y, a continuación, seleccione **Intro**.</span><span class="sxs-lookup"><span data-stu-id="a509e-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="a509e-117">En la pantalla de resultados, seleccione **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="a509e-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="a509e-118">Se abre una nueva ventana con una descripción de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="a509e-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="a509e-119">En la nueva ventana, en el cuadro de texto **Nombre** de archivo, proporcione un nombre de archivo para la copia de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="a509e-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="a509e-120">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a509e-120">Select **Create**.</span></span> <span data-ttu-id="a509e-121">Access descarga la base de datos Northwind y prepara el archivo.</span><span class="sxs-lookup"><span data-stu-id="a509e-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="a509e-122">Una vez completado este proceso, la base de datos se abre con una pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="a509e-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="a509e-123">Obtenga la base de datos de ejemplo AdventureWorks para SQL Server</span><span class="sxs-lookup"><span data-stu-id="a509e-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="a509e-124">Descargue la base de datos de ejemplo AdventureWorks para SQL Server desde el siguiente repositorio GitHub:</span><span class="sxs-lookup"><span data-stu-id="a509e-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="a509e-125">Bases de datos de ejemplo AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="a509e-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="a509e-126">Después de descargar uno\*de los archivos de copia de seguridad de base de datos (.bak), restaure la copia de seguridad en una instancia de SQL Server mediante SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a509e-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a509e-127">Consulte [Obtener SQL Server Management Studio](#get_ssms).</span><span class="sxs-lookup"><span data-stu-id="a509e-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a><span data-ttu-id="a509e-128">Obtenga SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a509e-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="a509e-129">Si desea ver o modificar una base de datos que ha descargado, puede usar SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a509e-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="a509e-130">Descargue SSMS desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="a509e-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="a509e-131">Descarga de SQL Server Management Studio (SSMS)</span><span class="sxs-lookup"><span data-stu-id="a509e-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="a509e-132">También puede ver y administrar bases de datos en el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a509e-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="a509e-133">En [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), conéctese a la base de datos desde el Explorador de objetos de SQL **ServerSQL Server**o cree una conexión de datos a la base de datos en el **Explorador**de servidores .</span><span class="sxs-lookup"><span data-stu-id="a509e-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="a509e-134">Abra estos paneles del explorador desde el menú **Ver.**</span><span class="sxs-lookup"><span data-stu-id="a509e-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a><span data-ttu-id="a509e-135">Obtener SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="a509e-135">Get SQL Server Express</span></span>

<span data-ttu-id="a509e-136">SQL Server Express es una edición gratuita de nivel de entrada de SQL Server que puede redistribuir con aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a509e-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="a509e-137">Descargue SQL Server Express desde la página siguiente:</span><span class="sxs-lookup"><span data-stu-id="a509e-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="a509e-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="a509e-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="a509e-139">Si usa [Visual Studio,](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)SQL Server Express LocalDB se incluye en la edición gratuita de la comunidad de Visual Studio, así como en las ediciones Professional y superior.</span><span class="sxs-lookup"><span data-stu-id="a509e-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a509e-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a509e-140">See also</span></span>

- [<span data-ttu-id="a509e-141">Introducción</span><span class="sxs-lookup"><span data-stu-id="a509e-141">Getting Started</span></span>](getting-started.md)
