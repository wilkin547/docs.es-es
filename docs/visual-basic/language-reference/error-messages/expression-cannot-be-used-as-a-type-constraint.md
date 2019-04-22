---
title: "'<expression>' no se puede utilizar como restricción de tipo"
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 8dbf510d7c6ee80e2dcd2f9d2552bc870413cbab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838110"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a>'\<expresión >' no puede utilizarse como una restricción de tipo
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
