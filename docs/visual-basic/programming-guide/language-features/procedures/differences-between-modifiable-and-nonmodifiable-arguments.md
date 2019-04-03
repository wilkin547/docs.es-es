---
title: Diferencias entre argumentos modificables y no modificables (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: a880ae8c13eebd5d9d325468098e058f58d3fa71
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826670"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Diferencias entre argumentos modificables y no modificables (Visual Basic)
Cuando se llama a un procedimiento, normalmente pass uno o más argumentos a él. Cada argumento corresponde a un elemento de programación subyacente. Los elementos subyacentes y los argumentos pueden ser modificable o no modificable.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Elementos modificables y no modificables  
 Un elemento de programación puede ser un *elemento modificable*, que puede tener su valor cambiado, o un *elemento no modificable*, que tiene un valor fijo, una vez que se ha creado.  
  
 En la tabla siguiente enumera los elementos de programación modificables y no modificables.  
  
|Puede modificables elementos|Elementos no modificables|  
|-------------------------|----------------------------|  
|Las variables locales (declaradas dentro de procedimientos), incluidas las variables de objeto, excepto de solo lectura|Propiedades, campos y variables de solo lectura|  
|Campos (variables de miembro de los módulos, clases y estructuras), excepto los de solo lectura|Constantes y literales|  
|Propiedades, excepto de solo lectura|Miembros de enumeración|  
|Elementos de matriz|Expresiones (incluso si sus elementos son modificables)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Argumentos modificables y no modificables  
 Un *argumento modificable* es uno con un elemento subyacente modificable. El código de llamada puede almacenar un nuevo valor en cualquier momento, y si se pasa el argumento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), el código en el procedimiento también puede modificar el elemento subyacente en el código de llamada.  
  
 Un *argumento no es modificable* tiene un elemento subyacente no modificable o se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). El procedimiento no puede modificar el elemento subyacente en el código que realiza la llamada, incluso si es un elemento modificable. Si es un elemento no modificable, el código de llamada no puede modificarla.  
  
 El procedimiento llamado podría modificar su copia local de un argumento no es modificable, pero esa modificación no afecta el elemento subyacente en el código de llamada.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Cómo: Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Cómo: Cambie el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Cómo: Proteger un argumento de procedimiento contra cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Cómo: Forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
