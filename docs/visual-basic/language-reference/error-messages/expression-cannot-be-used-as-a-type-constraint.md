---
title: '&#39;&lt;expresión&gt; &#39; no se puede usar como una restricción de tipo'
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: b7f77c8113f8af113b4c8515994093958970864a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742138"
---
# <a name="39ltexpressiongt39-cannot-be-used-as-a-type-constraint"></a>&#39;&lt;expresión&gt; &#39; no se puede usar como una restricción de tipo
Una lista de restricciones incluye una expresión que no representa una restricción válida en un parámetro de tipo.  
  
 Una lista de restricciones impone requisitos al argumento de tipo pasado al parámetro de tipo. Puede especificar los requisitos siguientes en cualquier combinación:  
  
-   El argumento de tipo debe implementar una o varias interfaces  
  
-   El argumento de tipo debe heredar de al menos una clase  
  
-   El argumento de tipo debe exponer un constructor sin parámetros al que el código de creación pueda acceder (incluya la restricción `New` ).  
  
 Si no incluye ninguna clase o interfaz específica en la lista de restricciones, puede imponer un requisito más general especificando uno de los elementos siguientes:  
  
-   El argumento de tipo debe ser un tipo de valor (incluya la restricción `Structure` ).  
  
-   El argumento de tipo debe ser un tipo de referencia (incluya la restricción `Class` ).  
  
 No es posible especificar `Structure` y `Class` para el mismo parámetro de tipo ni se pueden especificar estas restricciones más de una vez.  
  
 **Identificador de error:** BC32061  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe que la expresión y sus elementos estén escritos correctamente.  
  
-   Si la expresión no cumple los requisitos de la lista de requisitos anterior, quítela de la lista de restricciones.  
  
-   Si la expresión hace referencia a una interfaz o una clase, compruebe que el compilador tenga acceso a dicha interfaz o clase. Puede que deba calificar su nombre y quizás tenga que agregar una referencia al proyecto. Para obtener más información, vea "Referencias a proyectos" en [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Vea también
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

