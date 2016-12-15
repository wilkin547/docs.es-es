---
title: "Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interoperabilidad COM"
  - "interoperabilidad, objetos COM y .NET Framework"
  - "componentes compartidos"
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Interoperabilidad COM en aplicaciones .NET Framework (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Si desea utilizar objetos COM y objetos de .NET Framework en la misma aplicación, debe tener en cuenta las diferencias que existen en el modo en que los objetos residen en la memoria.  Un objeto de .NET Framework reside en la memoria administrada, es decir, en la memoria que controla Common Language Runtime, y el motor en tiempo de ejecución puede desplazarlo según sea necesario.  Un objeto COM reside en la memoria no administrada y no se prevé que se mueva a otra ubicación de la memoria.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] y [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] proporcionan las herramientas para controlar la interacción de estos componentes administrados y no administrados.  Para obtener más información sobre el código administrado, vea [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md).  
  
 Además de usar objetos COM en las aplicaciones .NET, es posible que también desee usar [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para desarrollar objetos accesibles a partir de código no administrado a través de COM.  
  
 Los vínculos de esta página proporcionan información detallada sobre las interacciones entre los objetos COM y los objetos de .NET Framework.  
  
## Secciones relacionadas  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 Proporciona vínculos a temas sobre la interoperabilidad COM en Visual Basic, incluidos los objetos COM, los controles ActiveX, las DLL Win32, los objetos administrados y la herencia de los objetos COM.  
  
 [COM Interop Wrapper Error](/visual-cpp/misc/com-interop-wrapper-error)  
 Explica las consecuencias y opciones en caso de que el sistema del proyecto no pueda crear un contenedor de interoperabilidad COM para un componente concreto.  
  
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)  
 Describe brevemente algunos de los problemas de la interacción entre el código administrado y no administrado, y proporciona vínculos a más información.  
  
 [COM Wrappers](../Topic/COM%20Wrappers.md)  
 Describe los contenedores invocables en tiempo de ejecución, que permiten que el código administrado llame a métodos COM, y los contenedores CCW, que permiten que los clientes COM llamen a métodos de objetos .NET.  
  
 [Advanced COM Interoperability](http://msdn.microsoft.com/es-es/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Proporciona vínculos a temas en los que se describe la interoperabilidad COM en lo que respecta a contenedores, excepciones, herencia, subprocesos, eventos, conversiones y cálculo de referencias.  
  
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)  
 Describe la herramienta que se puede utilizar para convertir las definiciones de tipos que se encuentran en una biblioteca de tipos COM en definiciones equivalentes en un ensamblado de Common Language Runtime.