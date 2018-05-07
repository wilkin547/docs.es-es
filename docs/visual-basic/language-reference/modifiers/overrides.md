---
title: Overrides (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 81118b9e97f320bffdbb58e5e1a2859052c4cee5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)
Especifica que una propiedad o procedimiento invalida una propiedad o procedimiento del mismo nombre heredado de una clase base.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Puede usar `Overrides` únicamente en una instrucción de declaración de procedimiento o propiedad.  
  
-   **Modificadores combinados.** No es posible especificar `Overrides` junto con `Shadows` o `Shared` en la misma declaración. Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.  
  
-   **Hacer coincidir las firmas.** La firma de esta declaración debe coincidir la *firma* de la propiedad o procedimiento que reemplaza. Esto significa que las listas de parámetros deben tener el mismo número de parámetros, en el mismo orden y con los mismos tipos de datos.  
  
     Además de coincidir con la firma, la declaración de reemplazo también debe coincidir de forma exacta con los elementos siguientes:  
  
    -   El nivel de acceso.  
  
    -   El tipo de valor devuelto, si lo hay.  
  
-   **Firmas genéricas.** En los procedimientos genéricos, la firma incluye el número de parámetros de tipo. Por lo tanto, la declaración de reemplazo también debe coincidir con la versión de la clase base en este sentido.  
  
-   **Coincidencia adicional.** Además de coincidir con la firma de la versión de la clase base, esta declaración también debe coincidir con los elementos siguientes:  
  
    -   Modificador de nivel de acceso (como [público](../../../visual-basic/language-reference/modifiers/public.md))  
  
    -   Mecanismo de paso de cada parámetro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))  
  
    -   Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.  
  
-   **Sombrear y reemplazar.** Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Si usa `Overrides`, el compilador agregará `Overloads` de forma implícita para que las API de biblioteca trabajen con C# más fácilmente.  
  
 El modificador `Overrides` se puede utilizar en los contextos siguientes:  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)  
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
