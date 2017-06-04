---
title: "C&#243;mo crear un proyecto LINQ to DataSet en Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo crear un proyecto LINQ to DataSet en Visual Studio
Los distintos tipos de proyecto [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] requieren determinados espacios de nombres importados \(Visual Basic\) o directivas `using` \(C\#\) y referencias.  El requisito mínimo es una referencia a System.Core.dll y una directiva `using` para <xref:System.Linq>.  De manera predeterminada, estos requisitos se proporcionan al crear un proyecto [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)].  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] también requiere una referencia a System.Data.dll y System.Data.DataSetExtensions.dll y una directiva `Imports` \(Visual Basic\) o `using` \(C\#\).  
  
 Si está actualizando a un proyecto desde una versión anterior de Visual Studio, es posible que tenga que proporcionar estas referencias relacionadas con LINQ de forma manual.  También es posible que tenga que configurar de forma manual el proyecto para establecer como destino la versión 3.5 de .NET Framework.  
  
> [!NOTE]
>  Si está creando el proyecto desde el símbolo del sistema, debe hacer referencia manualmente a las DLL relacionadas con LINQ en `drive`**:**\\Program Files\\Reference Assemblies\\Microsoft\\Framework\\v3.5.  
  
### Para establecer como destino .NET Framework  
  
1.  En [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], cree un proyecto nuevo de Visual Basic o C\#. Como alternativa, también puede abrir un proyecto de Visual Basic o C\# creado en Visual Studio 2005 y seguir las indicaciones para convertirlo en un proyecto [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Para un proyecto, haga clic en el menú **Proyecto** y, a continuación, haga clic en **Propiedades**.  
  
    1.  En la página de propiedades **Aplicación**, seleccione .NET Framework 3.5 en la lista desplegable **Marco de trabajo de destino**.  
  
3.  Para un proyecto Visual Basic, haga clic en el menú **Proyecto** y, a continuación, haga clic en **Propiedades**.  
  
    1.  En la página de propiedades **Compilación**, haga clic en **Opciones de compilación avanzadas** y, a continuación, seleccione .NET Framework 3.5 en la lista desplegable **Marco de trabajo de destino \(todas las configuraciones\)**.  
  
4.  En el menú **Proyecto**, haga clic en **Agregar referencia**, haga clic en la pestaña **.NET**, desplácese hasta **System.Core**, haga clic en él y, a continuación, haga clic en **Aceptar**.  
  
5.  Agregue una directiva `using` o un espacio de nombres importado para <xref:System.Linq> en el archivo de código origen o proyecto.  
  
     Para obtener más información, vea [using \(directiva\)](../Topic/using%20Directive%20\(C%23%20Reference\).md) o [Cómo: Agregar o quitar espacios de nombres importados \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
### Para habilitar la funcionalidad LINQ to DataSet  
  
1.  Si es necesario, siga las instrucciones descritas anteriormente para agregar una referencia a System.Core.dll y una directiva `using` o un espacio de nombres importado para System.Linq.  
  
2.  En C\# o Visual Basic, haga clic en el menú **Proyecto** y, a continuación, haga clic en **Agregar referencia**.  
  
3.  En el cuadro de diálogo **Agregar referencia**, haga clic en la pestaña **.NET** si no está en la parte superior.  Desplácese hasta **System.Data** y **System.Data.DataSetExtensions** y haga clic en ellos.  Haga clic en el botón **Aceptar**.  
  
4.  Agregue una directiva `using` o un espacio de nombres importado para <xref:System.Data> en el archivo de código origen o proyecto.  Para obtener más información, vea [using \(directiva\)](../Topic/using%20Directive%20\(C%23%20Reference\).md) o [Cómo: Agregar o quitar espacios de nombres importados \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
5.  Agregue una referencia a System.Data.DataSetExtensions.dll para la funcionalidad LINQ to Dataset.  Agregue una referencia a System.Data.dll si ésta no existe aún.  
  
6.  Si lo desea, agregue una directiva `using` o un espacio de nombres importado para `System.Data.Common` o `System.Data.SqlClient`, según cómo se conecte a la base de datos.  
  
## Vea también  
 [Introducción](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)   
 [Getting Started with LINQ](http://msdn.microsoft.com/es-es/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)