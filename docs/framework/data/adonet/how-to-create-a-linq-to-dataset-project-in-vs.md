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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3add191250a10d1d6016263ada0ba53fc8082717
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Cómo: Crear un proyecto de LINQ to DataSet en Visual Studio
Los distintos tipos de proyecto [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] requieren determinados espacios de nombres importados (Visual Basic) o directivas `using` (C#) y referencias. El requisito mínimo es una referencia a System.Core.dll y una directiva `using` para <xref:System.Linq>. De manera predeterminada, estos requisitos se proporcionan al crear un proyecto [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)]. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] también requiere una referencia a System.Data.dll y System.Data.DataSetExtensions.dll y una directiva `Imports` (Visual Basic) o `using` (C#).  
  
 Si está actualizando a un proyecto desde una versión anterior de Visual Studio, es posible que tenga que proporcionar estas referencias relacionadas con LINQ de forma manual. También es posible que tenga que configurar de forma manual el proyecto para establecer como destino la versión 3.5 de .NET Framework.  
  
> [!NOTE]
>  Si está generando desde un símbolo del sistema, deben hacer referencia manualmente las DLL relacionadas con LINQ en `drive` **:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.  
  
### <a name="to-target-the-net-framework-35"></a>Para establecer como destino .NET Framework  
  
1.  En [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], cree un proyecto Visual Basic o C# nuevo. Como alternativa, también puede abrir un proyecto Visual Basic o C# creado en Visual Studio 2005 y seguir las indicaciones para convertirlo en un proyecto [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Para un proyecto de C#, haga clic en el **proyecto** menú y, a continuación, haga clic en **propiedades**.  
  
    1.  En el **aplicación** página de propiedades, seleccione .NET Framework 3.5 en el **.NET Framework de destino** lista desplegable.  
  
3.  Para un proyecto de Visual Basic, haga clic en el **proyecto** menú y, a continuación, haga clic en **propiedades**.  
  
    1.  En el **compilar** página de propiedades, haga clic en **opciones de compilación avanzadas** y, a continuación, seleccione .NET Framework 3.5 en el **.NET Framework de destino (todas las configuraciones)** lista desplegable.  
  
4.  En el **proyecto** menú, haga clic en **Agregar referencia**, haga clic en el **.NET** ficha, desplácese hacia abajo hasta **System.Core**, haga clic en él y, a continuación, haga clic en  **Aceptar**.  
  
5.  Agregue una directiva `using` o un espacio de nombres importado para <xref:System.Linq> en el archivo de código origen o proyecto.  
  
     Para obtener más información, consulte [using (directiva)](~/docs/csharp/language-reference/keywords/using-directive.md) o [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
### <a name="to-enable-linq-to-dataset-functionality"></a>Para habilitar la funcionalidad LINQ to DataSet  
  
1.  Si es necesario, siga las instrucciones descritas anteriormente para agregar una referencia a System.Core.dll y una directiva `using` o un espacio de nombres importado para System.Linq.  
  
2.  En C# o Visual Basic, haga clic en el **proyecto** menú y, a continuación, haga clic en **Agregar referencia**.  
  
3.  En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** pestaña si no está en la parte superior. Desplácese hacia abajo hasta **System.Data** y **System.Data.DataSetExtensions** y haga clic en ellos. Haga clic en el **Aceptar** botón.  
  
4.  Agregue una directiva `using` o un espacio de nombres importado para <xref:System.Data> en el archivo de código origen o proyecto. Para obtener más información, consulte [using (directiva)](~/docs/csharp/language-reference/keywords/using-directive.md) o [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
5.  Agregue una referencia a System.Data.DataSetExtensions.dll para la funcionalidad LINQ to Dataset. Agregue una referencia a System.Data.dll si ésta no existe aún.  
  
6.  Si lo desea, agregue una directiva `using` o un espacio de nombres importado para `System.Data.Common` o `System.Data.SqlClient`, según cómo se conecte a la base de datos.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [introducción a LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
