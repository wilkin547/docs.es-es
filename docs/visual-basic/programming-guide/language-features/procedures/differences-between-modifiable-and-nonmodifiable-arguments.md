---
title: Diferencias entre argumentos modificables y no modificables
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 662ad3039bb3fd5c44847d5b2a97a033a18ad063
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071967"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Diferencias entre argumentos modificables y no modificables (Visual Basic)

Cuando se llama a un procedimiento, normalmente se pasan uno o más argumentos. Cada argumento corresponde a un elemento de programación subyacente. Tanto los elementos subyacentes como los argumentos pueden ser modificables o no modificables.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Elementos modificables y no modificables  

 Un elemento de programación puede ser un *elemento modificable*, cuyo valor se puede cambiar o un elemento no *modificable*, que tiene un valor fijo una vez que se ha creado.  
  
 En la tabla siguiente se enumeran los elementos de programación modificables y no modificables.  
  
|Elementos modificables|Elementos no modificables|  
|-------------------------|----------------------------|  
|Variables locales (declaradas dentro de los procedimientos), incluidas las variables de objeto, excepto para solo lectura|Variables, campos y propiedades de solo lectura|  
|Campos (variables miembro de módulos, clases y estructuras), excepto para solo lectura|Constantes y literales|  
|Propiedades, excepto para solo lectura|Miembros de enumeración|  
|Elementos de matriz|Expresiones (incluso si sus elementos son modificables)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Argumentos modificables y no modificables  

 Un *argumento modificable* es uno con un elemento subyacente modificable. El código de llamada puede almacenar un nuevo valor en cualquier momento y, si se pasa el argumento [ByRef](../../../language-reference/modifiers/byref.md), el código del procedimiento también puede modificar el elemento subyacente en el código de llamada.  
  
 Un *argumento no modificable* tiene un elemento subyacente no modificable o se pasa [ByVal](../../../language-reference/modifiers/byval.md). El procedimiento no puede modificar el elemento subyacente en el código de llamada, aunque sea un elemento modificable. Si es un elemento no modificable, el propio código de llamada no puede modificarlo.  
  
 El procedimiento llamado podría modificar su copia local de un argumento no modificable, pero esa modificación no afecta al elemento subyacente en el código de llamada.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedimiento para cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedimiento para forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md)
