---
title: "&#39; &lt;expresión&gt;&#39; no se puede usar como una restricción de tipo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords: BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 054c05747491afb02601df00225a703560cbe91c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39ltexpressiongt39-cannot-be-used-as-a-type-constraint"></a>&#39; &lt;expresión&gt;&#39; no se puede usar como una restricción de tipo
Una lista de restricciones incluye una expresión que no representa una restricción válida en un parámetro de tipo.  
  
 Una lista de restricciones impone requisitos al argumento de tipo pasado al parámetro de tipo. Puede especificar los requisitos siguientes en cualquier combinación:  
  
-   El argumento de tipo debe implementar una o varias interfaces  
  
-   El argumento de tipo debe heredar de al menos una clase  
  
-   El argumento de tipo debe exponer un constructor sin parámetros al que el código de creación pueda acceder (incluya la restricción `New` ).  
  
 Si no incluye ninguna clase o interfaz específica en la lista de restricciones, puede imponer un requisito más general especificando uno de los elementos siguientes:  
  
-   El argumento de tipo debe ser un tipo de valor (incluya la restricción `Structure` ).  
  
-   El argumento de tipo debe ser un tipo de referencia (incluya la restricción `Class` ).  
  
 No es posible especificar `Structure` y `Class` para el mismo parámetro de tipo ni se pueden especificar estas restricciones más de una vez.  
  
 **Id. de error:** BC32061  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe que la expresión y sus elementos estén escritos correctamente.  
  
-   Si la expresión no cumple los requisitos de la lista de requisitos anterior, quítela de la lista de restricciones.  
  
-   Si la expresión hace referencia a una interfaz o una clase, compruebe que el compilador tenga acceso a dicha interfaz o clase. Puede que deba calificar su nombre y quizás tenga que agregar una referencia al proyecto. Para obtener más información, vea "Referencias a proyectos" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Vea también  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Tipos de valores y tipos de referencias](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [NO ESTÁ EN LA COMPILACIÓN: Cómo: agregar o quitar referencias mediante el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
