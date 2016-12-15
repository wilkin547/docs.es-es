---
title: "C&#243;mo: Crear un m&#233;todo nuevo para una enumeraci&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "extensibilidad de enum [C#]"
  - "enumeraciones [C#]"
  - "métodos de extensión [C#], para las enumeraciones"
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Crear un m&#233;todo nuevo para una enumeraci&#243;n (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Puede utilizar métodos de extensión para agregar funcionalidad específica a un tipo de enumeración concreto.  
  
## Ejemplo  
 En el ejemplo siguiente, la enumeración `Grades` representa las posibles calificaciones con letras que un alumno puede recibir en una clase.  Un método de extensión denominado `Passing` se agrega al tipo `Grades` para que cada instancia de ese tipo "sepa" si representa una calificación de aprobado o no.  
  
 [!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 Observe que la clase `Extensions` también contiene una variable estática que se actualiza dinámicamente y que el valor devuelto del método de extensión refleja el valor actual de dicha variable.  Esto demuestra que, en segundo plano, los métodos de extensión se invocan directamente en la clase estática en la que se definen.  
  
## Compilar el código  
 Para ejecutar este código, debe copiarlo y pegarlo en un proyecto de aplicación de consola de Visual C\# creado en [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)].  De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] y contiene una referencia a System.Core.dll y una directiva `using` para System.Linq.  Si el proyecto no cumple uno o varios de estos requisitos, puede agregar lo que falte manualmente.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)