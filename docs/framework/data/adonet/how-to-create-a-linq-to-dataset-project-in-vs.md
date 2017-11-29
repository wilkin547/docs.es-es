---
title: "Cómo: Crear un proyecto de LINQ to DataSet en Visual Studio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 192273c6d364cebe828965ed016eea81135602f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="c3b72-102">Cómo: Crear un proyecto de LINQ to DataSet en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c3b72-102">How to: Create a LINQ to DataSet Project In Visual Studio</span></span>
<span data-ttu-id="c3b72-103">Los distintos tipos de proyecto [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] requieren determinados espacios de nombres importados (Visual Basic) o directivas `using` (C#) y referencias.</span><span class="sxs-lookup"><span data-stu-id="c3b72-103">The different types of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] projects require certain imported namespaces (Visual Basic) or `using` directives (C#) and references.</span></span> <span data-ttu-id="c3b72-104">El requisito mínimo es una referencia a System.Core.dll y una directiva `using` para <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="c3b72-104">The minimum requirement is a reference to System.Core.dll and a `using` directive for <xref:System.Linq>.</span></span> <span data-ttu-id="c3b72-105">De manera predeterminada, estos requisitos se proporcionan al crear un proyecto [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3b72-105">By default, these are supplied if you create a new [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] project.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="c3b72-106"> también requiere una referencia a System.Data.dll y System.Data.DataSetExtensions.dll y una directiva `Imports` (Visual Basic) o `using` (C#).</span><span class="sxs-lookup"><span data-stu-id="c3b72-106"> also requires a reference to System.Data.dll and System.Data.DataSetExtensions.dll and an `Imports` (Visual Basic) or `using` (C#) directive.</span></span>  
  
 <span data-ttu-id="c3b72-107">Si está actualizando a un proyecto desde una versión anterior de Visual Studio, es posible que tenga que proporcionar estas referencias relacionadas con LINQ de forma manual.</span><span class="sxs-lookup"><span data-stu-id="c3b72-107">If you are upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span> <span data-ttu-id="c3b72-108">También es posible que tenga que configurar de forma manual el proyecto para establecer como destino la versión 3.5 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3b72-108">You might also have to manually set the project to target the .NET Framework version 3.5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3b72-109">Si está generando desde un símbolo del sistema, deben hacer referencia manualmente las DLL relacionadas con LINQ en `drive` **:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.</span><span class="sxs-lookup"><span data-stu-id="c3b72-109">If you are building from a command prompt, you must manually reference the LINQ-related DLLs in `drive`**:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.</span></span>  
  
### <a name="to-target-the-net-framework-35"></a><span data-ttu-id="c3b72-110">Para establecer como destino .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c3b72-110">To target the .NET Framework 3.5</span></span>  
  
1.  <span data-ttu-id="c3b72-111">En [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], cree un proyecto Visual Basic o C# nuevo.</span><span class="sxs-lookup"><span data-stu-id="c3b72-111">In [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], create a new Visual Basic or C# project.</span></span> <span data-ttu-id="c3b72-112">Como alternativa, también puede abrir un proyecto Visual Basic o C# creado en Visual Studio 2005 y seguir las indicaciones para convertirlo en un proyecto [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3b72-112">Alternatively, you can open a Visual Basic or C# project that was created in Visual Studio 2005 and follow the prompts to convert it to a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="c3b72-113">Para un proyecto de C#, haga clic en el **proyecto** menú y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c3b72-113">For a C# project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="c3b72-114">En el **aplicación** página de propiedades, seleccione .NET Framework 3.5 en el **.NET Framework de destino** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c3b72-114">In the **Application** property page, select .NET Framework 3.5 in the **Target Framework** drop-down list.</span></span>  
  
3.  <span data-ttu-id="c3b72-115">Para un proyecto de Visual Basic, haga clic en el **proyecto** menú y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c3b72-115">For a Visual Basic project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="c3b72-116">En el **compilar** página de propiedades, haga clic en **opciones de compilación avanzadas** y, a continuación, seleccione .NET Framework 3.5 en el **.NET Framework de destino (todas las configuraciones)** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c3b72-116">In the **Compile** property page, click **Advanced Compile Options** and then select .NET Framework 3.5 in the **Target Framework (all configurations)** drop-down list.</span></span>  
  
4.  <span data-ttu-id="c3b72-117">En el **proyecto** menú, haga clic en **Agregar referencia**, haga clic en el **.NET** ficha, desplácese hacia abajo hasta **System.Core**, haga clic en él y, a continuación, haga clic en  **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3b72-117">On the **Project** menu, click **Add Reference**, click the **.NET** tab, scroll down to **System.Core**, click it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c3b72-118">Agregue una directiva `using` o un espacio de nombres importado para <xref:System.Linq> en el archivo de código origen o proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3b72-118">Add a `using` directive or imported namespace for <xref:System.Linq> to your source code file or project.</span></span>  
  
     <span data-ttu-id="c3b72-119">Para obtener más información, consulte [using (directiva)](~/docs/csharp/language-reference/keywords/using-directive.md) o [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c3b72-119">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
### <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="c3b72-120">Para habilitar la funcionalidad LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="c3b72-120">To enable LINQ to DataSet functionality</span></span>  
  
1.  <span data-ttu-id="c3b72-121">Si es necesario, siga las instrucciones descritas anteriormente para agregar una referencia a System.Core.dll y una directiva `using` o un espacio de nombres importado para System.Linq.</span><span class="sxs-lookup"><span data-stu-id="c3b72-121">If necessary, follow the steps earlier in this topic to add a reference to System.Core.dll and a `using` directive or imported namespace for System.Linq.</span></span>  
  
2.  <span data-ttu-id="c3b72-122">En C# o Visual Basic, haga clic en el **proyecto** menú y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="c3b72-122">In C# or Visual Basic, click the **Project** menu, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="c3b72-123">En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** pestaña si no está en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="c3b72-123">In the **Add Reference** dialog box, click the **.NET** tab if it is not on top.</span></span> <span data-ttu-id="c3b72-124">Desplácese hacia abajo hasta **System.Data** y **System.Data.DataSetExtensions** y haga clic en ellos.</span><span class="sxs-lookup"><span data-stu-id="c3b72-124">Scroll down to **System.Data** and **System.Data.DataSetExtensions** and click on them.</span></span> <span data-ttu-id="c3b72-125">Haga clic en el **Aceptar** botón.</span><span class="sxs-lookup"><span data-stu-id="c3b72-125">Click the **OK** button.</span></span>  
  
4.  <span data-ttu-id="c3b72-126">Agregue una directiva `using` o un espacio de nombres importado para <xref:System.Data> en el archivo de código origen o proyecto.</span><span class="sxs-lookup"><span data-stu-id="c3b72-126">Add a `using` directive or imported namespace for <xref:System.Data> to your source code file or project.</span></span> <span data-ttu-id="c3b72-127">Para obtener más información, consulte [using (directiva)](~/docs/csharp/language-reference/keywords/using-directive.md) o [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c3b72-127">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
5.  <span data-ttu-id="c3b72-128">Agregue una referencia a System.Data.DataSetExtensions.dll para la funcionalidad LINQ to Dataset.</span><span class="sxs-lookup"><span data-stu-id="c3b72-128">Add a reference to System.Data.DataSetExtensions.dll for LINQ to Dataset functionality.</span></span> <span data-ttu-id="c3b72-129">Agregue una referencia a System.Data.dll si ésta no existe aún.</span><span class="sxs-lookup"><span data-stu-id="c3b72-129">Add a reference to System.Data.dll if it does not already exist.</span></span>  
  
6.  <span data-ttu-id="c3b72-130">Si lo desea, agregue una directiva `using` o un espacio de nombres importado para `System.Data.Common` o `System.Data.SqlClient`, según cómo se conecte a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3b72-130">Optionally, add a `using` directive or imported namespace for `System.Data.Common` or `System.Data.SqlClient`, depending on how you connect to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b72-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3b72-131">See Also</span></span>  
 [<span data-ttu-id="c3b72-132">Introducción</span><span class="sxs-lookup"><span data-stu-id="c3b72-132">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [<span data-ttu-id="c3b72-133">introducción a LINQ</span><span class="sxs-lookup"><span data-stu-id="c3b72-133">Getting Started with LINQ</span></span>](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
