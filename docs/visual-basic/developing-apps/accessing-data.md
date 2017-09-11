---
title: Obtener acceso a datos en aplicaciones de Visual Basic
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data [Visual Basic]
- Visual Basic, data access
ms.assetid: 3086ab38-3be5-4b22-9385-7d0e16b04f6a
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4ff9885f66171ee0454bff058b342d1b5683d3e3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-data-in-visual-basic-applications"></a><span data-ttu-id="61933-102">Obtener acceso a datos en aplicaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61933-102">Accessing data in Visual Basic applications</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="61933-103"> incluye varias características nuevas que ayudan en el desarrollo de aplicaciones que tienen acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="61933-103"> includes several new features to assist in developing applications that access data.</span></span> <span data-ttu-id="61933-104">Los formularios enlazados a datos para aplicaciones Windows se crean arrastrando elementos desde la [ventana Orígenes de datos](/visualstudio/data-tools/add-new-data-sources) hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="61933-104">Data-bound forms for Windows applications are created by dragging items from the [Data Sources Window](/visualstudio/data-tools/add-new-data-sources) onto the form.</span></span> <span data-ttu-id="61933-105">Se puede enlazar controles a datos arrastrando elementos desde la **ventana de orígenes de datos** a los controles existentes.</span><span class="sxs-lookup"><span data-stu-id="61933-105">You bind controls to data by dragging items from the **Data Sources Window** onto existing controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="61933-106">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="61933-106">Related sections</span></span>  
 [<span data-ttu-id="61933-107">Obtener acceso a los datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="61933-107">Accessing Data in Visual Studio</span></span>](/visualstudio/data-tools/)  
 <span data-ttu-id="61933-108">Proporciona vínculos a páginas que tratan sobre la incorporación de funcionalidad de acceso a datos a sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="61933-108">Provides links to pages that discuss incorporating data access functionality into your applications.</span></span>

 [<span data-ttu-id="61933-109">Visual Studio Data Tools para .NET</span><span class="sxs-lookup"><span data-stu-id="61933-109">Visual Studio data tools for .NET</span></span>](/visualstudio/data-tools/visual-studio-data-tools-for-dotnet)  
 <span data-ttu-id="61933-110">Proporciona vínculos a páginas que describen la creación de aplicaciones que funcionan con datos mediante [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61933-110">Provides links to pages on creating applications that work with data, using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
 [<span data-ttu-id="61933-111">LINQ</span><span class="sxs-lookup"><span data-stu-id="61933-111">LINQ</span></span>](../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="61933-112">Proporciona vínculos a temas en los que se describe cómo usar LINQ en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="61933-112">Provides links to topics that describe how to use LINQ with Visual Basic.</span></span>  
  
 [<span data-ttu-id="61933-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="61933-113">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)  
 <span data-ttu-id="61933-114">Proporciona información sobre [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61933-114">Provides information about [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="61933-115">Incluye ejemplos de programación.</span><span class="sxs-lookup"><span data-stu-id="61933-115">Includes programming examples.</span></span>  
  
 [<span data-ttu-id="61933-116">Herramientas LINQ to SQL en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="61933-116">LINQ to SQL Tools in Visual Studio</span></span>](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)  
 <span data-ttu-id="61933-117">Proporciona vínculos a temas sobre cómo crear un modelo de objetos [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) en aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="61933-117">Provides links to topics about how to create a [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) object model in applications.</span></span>  
  
 [<span data-ttu-id="61933-118">Trabajar con conjuntos de datos en aplicaciones de n capas</span><span class="sxs-lookup"><span data-stu-id="61933-118">Work with datasets in n-tier applications</span></span>](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)  
 <span data-ttu-id="61933-119">Proporciona vínculos a temas sobre cómo crear aplicaciones de datos de niveles múltiples.</span><span class="sxs-lookup"><span data-stu-id="61933-119">Provides links to topics about how to create multitiered data applications.</span></span>  
     
 [<span data-ttu-id="61933-120">Agregar nuevas conexiones</span><span class="sxs-lookup"><span data-stu-id="61933-120">Add new connections</span></span>](/visualstudio/data-tools/add-new-connections)  
 <span data-ttu-id="61933-121">Proporciona vínculos a páginas sobre la conexión de la aplicación a datos con herramientas en tiempo de diseño y objetos de conexión ADO.NET, mediante [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61933-121">Provides links to pages on connecting your application to data with design-time tools and ADO.NET connection objects, using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  

 [<span data-ttu-id="61933-122">Herramientas de conjuntos de datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="61933-122">Dataset Tools in Visual Studio</span></span>](/visualstudio/data-tools/dataset-tools-in-visual-studio)  
 <span data-ttu-id="61933-123">Proporciona vínculos a páginas que describen cómo cargar datos en los conjuntos de datos y cómo ejecutar instrucciones SQL y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="61933-123">Provides links to pages describing how to load data into datasets and how to execute SQL statements and stored procedures.</span></span>  
  
 [<span data-ttu-id="61933-124">Enlazar controles a los datos en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="61933-124">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)  
 <span data-ttu-id="61933-125">Proporciona vínculos a páginas que explican cómo se muestran datos en Windows Forms mediante controles enlazados a datos.</span><span class="sxs-lookup"><span data-stu-id="61933-125">Provides links to pages that explain how to display data on Windows Forms through data-bound controls.</span></span>  
  
 [<span data-ttu-id="61933-126">Editar datos en conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="61933-126">Edit Data in Datasets</span></span>](/visualstudio/data-tools/edit-data-in-datasets)  
 <span data-ttu-id="61933-127">Proporciona vínculos a páginas que describen cómo manipular los datos en las tablas de datos de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="61933-127">Provides links to pages describing how to manipulate the data in the data tables of a dataset.</span></span>  
  
 [<span data-ttu-id="61933-128">Validar los datos en conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="61933-128">Validate data in datasets</span></span>](/visualstudio/data-tools/validate-data-in-datasets)  
 <span data-ttu-id="61933-129">Proporciona vínculos a páginas que describen cómo agregar validación a un conjunto de datos durante los cambios de columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="61933-129">Provides links to pages describing how to add validation to a dataset during column and row changes.</span></span>  
  
 [<span data-ttu-id="61933-130">Guardar los datos de nuevo en la base de datos</span><span class="sxs-lookup"><span data-stu-id="61933-130">Save data back to the database</span></span>](/visualstudio/data-tools/save-data-back-to-the-database)  
 <span data-ttu-id="61933-131">Proporciona vínculos a páginas que explican cómo enviar datos actualizados de una aplicación a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61933-131">Provides links to pages explaining how to send updated data from an application to the database.</span></span>  
  
 [<span data-ttu-id="61933-132">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="61933-132">ADO.NET</span></span>](https://msdn.microsoft.com/library/e80y5yhx.aspx)  
 <span data-ttu-id="61933-133">Describe las clases ADO.NET que exponen servicios de acceso a datos al programador de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61933-133">Describes the ADO.NET classes, which expose data-access services to the .NET Framework programmer.</span></span>

 [<span data-ttu-id="61933-134">Datos en las soluciones de Office</span><span class="sxs-lookup"><span data-stu-id="61933-134">Data in Office Solutions</span></span>](https://msdn.microsoft.com/library/xx069ybh)  
 <span data-ttu-id="61933-135">Contiene vínculos a páginas que explican el funcionamiento de los datos en las soluciones de Office, incluida información sobre programación orientada a esquemas, almacenamiento de datos en memoria caché y acceso a datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="61933-135">Contains links to pages that explain how data works in Office solutions, including information about schema-oriented programming, data caching, and server-side data access.</span></span>

