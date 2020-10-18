---
title: "'<expression>' no se puede utilizar como restricción de tipo"
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 6e55bfdc175f285b335512e64f4c2407bdb0e8c7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163095"
---
# <a name="bc32061-expression-cannot-be-used-as-a-type-constraint"></a>BC32061: ' \<expression> ' no se puede usar como restricción de tipo

Una lista de restricciones incluye una expresión que no representa una restricción válida en un parámetro de tipo.

 Una lista de restricciones impone requisitos al argumento de tipo pasado al parámetro de tipo. Puede especificar los requisitos siguientes en cualquier combinación:

- El argumento de tipo debe implementar una o varias interfaces

- El argumento de tipo debe heredar de al menos una clase

- El argumento de tipo debe exponer un constructor sin parámetros al que el código de creación pueda acceder (incluya la restricción `New` ).

 Si no incluye ninguna clase o interfaz específica en la lista de restricciones, puede imponer un requisito más general especificando uno de los elementos siguientes:

- El argumento de tipo debe ser un tipo de valor (incluya la restricción `Structure` ).

- El argumento de tipo debe ser un tipo de referencia (incluya la restricción `Class` ).

 No es posible especificar `Structure` y `Class` para el mismo parámetro de tipo y no se pueden especificar estas restricciones más de una vez.

 **Identificador de error:** BC32061

## <a name="to-correct-this-error"></a>Para corregir este error

- Compruebe que la expresión y sus elementos estén escritos correctamente.

- Si la expresión no cumple los requisitos de la lista de requisitos anterior, quítela de la lista de restricciones.

- Si la expresión hace referencia a una interfaz o una clase, compruebe que el compilador tenga acceso a dicha interfaz o clase. Puede que deba calificar su nombre y quizás tenga que agregar una referencia al proyecto. Para obtener más información, vea "referencias a proyectos" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

## <a name="see-also"></a>Vea también

- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Tipos de valor y tipos de referencia](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
