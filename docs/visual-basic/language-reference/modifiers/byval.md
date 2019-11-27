---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351597"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Especifica que un argumento se pasa [por valor](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), de modo que el procedimiento o la propiedad a los que se ha llamado no pueden cambiar el valor de una variable subyacente del argumento en el código de llamada. Si no se especifica ningún modificador, ByVal es el valor predeterminado.

> [!NOTE]
> Dado que es el valor predeterminado, no es necesario especificar explícitamente la palabra clave `ByVal` en las firmas de método. Tiende a producir código ruidoso y, a menudo, conduce a la palabra clave de `ByRef` no predeterminada que se pasa por alto.

## <a name="remarks"></a>Comentarios
 El modificador `ByVal` se puede utilizar en los contextos siguientes:

 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)

 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a>Ejemplo
 En el siguiente ejemplo se muestra el uso del mecanismo de paso de parámetros `ByVal` con un argumento de tipo de referencia. En el ejemplo, el argumento es `c1`, una instancia de la clase `Class1`. `ByVal` evita que el código de los procedimientos cambie el valor subyacente del argumento de referencia, `c1`, pero no protege los campos y propiedades accesibles de `c1`.

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>Vea también

- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Paso de argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
