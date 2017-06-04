---
title: "Compiling an Interop Project | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "interoperation with unmanaged code, compiling"
  - "COM interop, compiling"
  - "exposing COM components to .NET Framework"
  - "compiling interop projects"
  - "interoperation with unmanaged code, exposing COM components"
  - "COM interop, exposing COM components"
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Compiling an Interop Project
Los proyectos de interoperabilidad COM que hacen referencia a uno o varios ensamblados que contienen tipos COM importados se compilan del mismo modo que cualquier otro proyecto administrado.  Puede hacer referencia a los ensamblados de interoperabilidad en un entorno de desarrollo como Visual Studio o puede hacer referencia a ellos al utilizar un compilador de línea de comandos.  En cualquier caso, para que se compile correctamente, el ensamblado de interoperabilidad debe estar en el mismo directorio que el resto de los archivos del proyecto.  
  
 Hay dos maneras de hacer referencia a los ensamblados de interoperabilidad:  
  
-   Tipos de interoperabilidad incrustados: a partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] y [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], puede indicar al compilador que incruste información de tipos desde un ensamblado de interoperabilidad en el ejecutable.  Esta es la técnica recomendada.  
  
-   Implementando ensamblados de interoperabilidad: puede crear una referencia estándar a un ensamblado de interoperabilidad.  En este caso, el ensamblado de interoperabilidad se debe implementar con la aplicación.  
  
 Las diferencias entre estas dos técnicas se describen con mayor detalle en [Using COM Types in Managed Code](http://msdn.microsoft.com/es-es/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
 La incrustación de tipos de interoperabilidad con Visual Studio se muestra en [Tutorial: Incrustar información de tipos de los ensamblados de Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md) y [Tutorial: Incrustar los tipos de los ensamblados administrados](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Para hacer referencia a un ensamblado de interoperabilidad con un compilador de línea de comandos e incrustar información de tipos en los ejecutables, utilice el modificador del compilador [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md) o [\/link](../Topic/-link%20\(Visual%20Basic\).md) y especifique el nombre del ensamblado de interoperabilidad.  
  
> [!NOTE]
>  Las aplicaciones de Visual C\+\+ no pueden incrustar información de tipos, pero pueden interoperar con aplicaciones o complementos que lo hagan.  
  
 Para compilar una aplicación que incluye un ensamblado de interoperabilidad primario cuando se implementa, utilice el modificador del compilador **\/reference** y especifique el nombre del ensamblado de interoperabilidad.  
  
## Vea también  
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Independencia del lenguaje y componentes independientes del lenguaje](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/es-es/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Tutorial: Incrustar información de tipos de los ensamblados de Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tutorial: Incrustar los tipos de los ensamblados administrados](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)