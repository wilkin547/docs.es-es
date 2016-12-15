---
title: "&#39;&lt;expresi&#243;n&gt;&#39; no se puede utilizar como restricci&#243;n de tipo | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32061"
  - "vbc32061"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32061"
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;expresi&#243;n&gt;&#39; no se puede utilizar como restricci&#243;n de tipo
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una lista de restricciones incluye una expresión que no representa una restricción válida en un parámetro de tipo.  
  
 Una lista de restricciones impone requisitos al argumento de tipo que se pasa al parámetro de tipo.  Puede especificar los siguientes requisitos en cualquier combinación:  
  
-   El argumento de tipo debe implementar una o más interfaces  
  
-   El argumento de tipo se debe heredar, como máximo, de una clase  
  
-   El argumento de tipo debe exponer un constructor sin parámetros al que el código creado puede tener acceso \(incluya la restricción `New`\)  
  
 Si no se incluye una clase o interfaz específica en la lista de restricciones, se puede imponer un requisito más general especificando uno de los siguientes:  
  
-   El argumento de tipo debe ser un tipo de valor \(incluya la restricción `Structure`\).  
  
-   El argumento de tipo debe ser un tipo de referencia \(incluya la restricción `Class`\).  
  
 `Structure` y `Class` no pueden especificarse simultáneamente para un mismo parámetro de tipo; tampoco pueden especificarse por separado más de una vez.  
  
 **Identificador de error:** BC32061  
  
### Para corregir este error  
  
-   Compruebe que la expresión y sus elementos se han escrito correctamente.  
  
-   Si la expresión no cumple la lista anterior de requisitos, quítela de la lista de restricciones.  
  
-   Si se hace referencia a la expresión en una interfaz o clase, compruebe que el compilador tiene acceso a dicha interfaz o clase.  Podría necesitar calificar su nombre y podría necesitar agregar una referencia a su proyecto.  Para obtener más información, vea "Referencias a proyectos" en [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## Vea también  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Tipos de valor y tipos de referencia](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Cómo: Agregar o quitar referencias utilizando el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/es-es/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)