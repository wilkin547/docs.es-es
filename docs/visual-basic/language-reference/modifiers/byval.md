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
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373029"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Especifica que un argumento se pasa [por valor](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), de modo que el procedimiento o la propiedad a los que se ha llamado no pueden cambiar el valor de una variable subyacente del argumento en el código de llamada. Si no se especifica ningún modificador, ByVal es el valor predeterminado.

> [!NOTE]
> Dado que es el valor predeterminado, no es necesario especificar explícitamente la `ByVal` palabra clave en las firmas de método. Tiende a generar código ruidoso y a menudo conduce a que la `ByRef` palabra clave no predeterminada se desechara.

## <a name="remarks"></a>Observaciones
 El modificador `ByVal` se puede utilizar en los contextos siguientes:

 [Declare Statement](../statements/declare-statement.md)

 [Instrucción Function](../statements/function-statement.md)
  
 [Operator Statement](../statements/operator-statement.md)
  
 [Property Statement](../statements/property-statement.md)
  
 [Instrucción Sub](../statements/sub-statement.md)

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se muestra el uso del `ByVal` mecanismo de paso de parámetros con un argumento de tipo de referencia. En el ejemplo, el argumento es `c1` , una instancia de clase `Class1` . `ByVal`evita que el código de los procedimientos cambie el valor subyacente del argumento de referencia, `c1` , pero no protege los campos y propiedades accesibles de `c1` .

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>Consulte también

- [Palabras clave](../keywords/index.md)
- [Pasar argumentos por valor y por referencia](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
