---
title: "Importing a Type Library as an Assembly | Microsoft Docs"
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
  - "importing type library"
  - "type metadata"
  - "custom wrappers"
  - "metadata"
  - "exposing COM components to .NET Framework"
  - "Type Library Importer"
  - "interoperation with unmanaged code, importing type library"
  - "interoperation with unmanaged code, exposing COM components"
  - "type libraries"
  - "TypeLibConverter class, importing type library as assembly"
  - "COM interop, importing type library"
  - "COM interop, exposing COM components"
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Importing a Type Library as an Assembly
Normalmente, las definiciones de tipos COM residen en una biblioteca de tipos.  Por otro lado, los compiladores conformes a CLS producen metadatos de tipos en un ensamblado.  Los dos orígenes de información de tipos son muy diferentes.  En este tema se describen las técnicas para generar metadatos a partir de una biblioteca de tipos.  El ensamblado resultante se denomina ensamblado de interoperabilidad y la información de tipos que contiene permite a las aplicaciones de .NET Framework utilizar tipos COM.  
  
 Hay dos maneras de hacer que esta información de tipos esté disponible para la aplicación:  
  
-   Usando ensamblados de interoperabilidad de tiempo de diseño únicamente: a partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede indicar al compilador que incruste información de tipo del ensamblado de interoperabilidad de una aplicación ejecutable.  El compilador incrusta solo la información de tipo que la aplicación utiliza.  No es necesario implementar el ensamblado de interoperabilidad con la aplicación.  Esta es la técnica recomendada.  
  
-   Implementando ensamblados de interoperabilidad: puede crear una referencia estándar al ensamblado de interoperabilidad.  En este caso, el ensamblado de interoperabilidad se debe implementar con la aplicación.  Si utiliza esta técnica y no usa ningún componente COM privado, haga siempre referencia al ensamblado de interoperabilidad primario \(PIA\) publicado por el autor del componente COM que prevé incorporar en el código administrado.  Para obtener más información sobre la creación y el uso de ensamblados de interoperabilidad primarios, vea [Ensamblados de interoperabilidad primarios](http://msdn.microsoft.com/es-es/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
 Al utilizar ensamblados de interoperabilidad de tiempo de diseño, puede incrustar información de tipos del ensamblado de interoperabilidad primario publicado por el autor del componente COM.  Sin embargo, no es necesario implementar el ensamblado de interoperabilidad primario con la aplicación.  
  
 Al utilizar ensamblados de interoperabilidad de tiempo de diseño, se reduce el tamaño de la aplicación, porque la mayoría de las aplicaciones no utilizan todas las características de un componente COM.  El compilador es muy eficaz cuando incrusta información de tipos; si la aplicación solo utiliza algunos de los métodos de una interfaz COM, el compilador no incrusta los métodos no usados.  Cuando una aplicación que ha incrustado información de tipos interactúa con otra aplicación, o interactúa con una aplicación que utiliza un ensamblado de interoperabilidad primario, Common Language Runtime utiliza las reglas de equivalencia de tipos para determinar si dos tipos con el mismo nombre representan el mismo tipo COM.  No es preciso conocerlas para utilizar objetos COM.  Ahora bien, si le interesan las reglas, vea [Type Equivalence and Embedded Interop Types](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md).  
  
## Generar metadatos  
 Las bibliotecas de tipos COM pueden ser archivos independientes con una extensión .tlb, como Loanlib.tlb.  Algunas bibliotecas de tipos se insertan en la sección de recursos de un archivo .dll o .exe.  Otros orígenes de información de bibliotecas de tipos son los archivos .olb y .ocx.  
  
 Una vez que se localice la biblioteca de tipos que contiene la implementación del tipo COM de destino, puede elegir una de las siguientes opciones para generar un ensamblado que contenga metadatos de tipos.  
  
-   Visual Studio  
  
     Visual Studio convierte automáticamente los tipos COM de una biblioteca de tipos en metadatos de un ensamblado.  Para obtener instrucciones, vea [Cómo: Agregar referencias a bibliotecas de tipos](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) y [Tutorial: Incrustar información de tipos de los ensamblados de Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   [Importador de la biblioteca de tipos \(TlbImp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     El Importador de la biblioteca de tipos proporciona opciones de línea de comandos para ajustar los metadatos del archivo de ensamblado resultante, importa tipos de una biblioteca de tipos existente y genera un ensamblado y un espacio de nombres.  Para obtener instrucciones, vea [Cómo: Generar ensamblados de interoperabilidad a partir de bibliotecas de tipos](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).  
  
-   Clase <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=fullName>  
  
     Esta clase proporciona los métodos para convertir coclases e interfaces de una biblioteca de tipos en metadatos de un ensamblado.  Genera los mismos metadatos que Tlbimp.exe.  Sin embargo, a diferencia de Tlbimp.exe, la clase <xref:System.Runtime.InteropServices.TypeLibConverter> puede convertir una biblioteca de tipos en memoria en metadatos.  
  
-   Contenedores personalizados  
  
     Si una biblioteca de tipos no está disponible o no es válida, tiene la opción de crear una definición duplicada de la clase o interfaz en código fuente administrado.  A continuación, puede compilar el código fuente con un compilador orientado a Common Language Runtime para generar metadatos en un ensamblado.  
  
     Para definir tipos COM manualmente, necesita los siguientes elementos:  
  
    -   Descripciones precisas de las coclases e interfaces que se van a definir.  
  
    -   Un compilador, como el compilador de C\#, que pueda generar las definiciones de clase de .NET Framework adecuadas.  
  
    -   Conocimiento de las reglas de conversión de bibliotecas de tipos en ensamblados.  
  
     Escribir un contenedor personalizado es una técnica avanzada.  Para obtener más información acerca de la forma de generar un contenedor personalizado, vea [Personalizar contenedores estándar](http://msdn.microsoft.com/es-es/c40d089b-6a3c-41b5-a20d-d760c215e49d).  
  
 Para obtener información detallada sobre el proceso de importación de interoperabilidad COM, vea [Resumen de la conversión de bibliotecas de tipos en ensamblados](http://msdn.microsoft.com/es-es/bf3f90c5-4770-4ab8-895c-3ba1055cc958).  
  
## Vea también  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/es-es/bf3f90c5-4770-4ab8-895c-3ba1055cc958)   
 [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/es-es/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/es-es/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Compiling an Interop Project](../../../docs/framework/interop/compiling-an-interop-project.md)   
 [Deploying an Interop Application](../../../docs/framework/interop/deploying-an-interop-application.md)   
 [How to: Add References to Type Libraries](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)   
 [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)   
 [Tutorial: Incrustar información de tipos de los ensamblados de Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)