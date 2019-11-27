---
title: IsTrue (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349512"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue (Operador) (Visual Basic)
Determina si una expresión es `True`.  
  
 No se puede llamar a `IsTrue` explícitamente en el código, pero el compilador Visual Basic puede usarlo para generar código a partir de cláusulas `OrElse`. Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una cláusula `OrElse`, debe definir `IsTrue` en esa clase o estructura.  
  
 El compilador tiene en cuenta los operadores `IsTrue` y `IsFalse` como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilador de IsTrue  
 Cuando haya definido una clase o estructura, puede usar una variable de ese tipo en una instrucción `For`, `If`, `Else If`o `While`, o en una cláusula `When`. Si lo hace, el compilador requiere un operador que convierta el tipo en un valor `Boolean` para que pueda probar una condición. Busca un operador adecuado en el orden siguiente:  
  
1. Operador de conversión de ampliación de la clase o estructura que se va a `Boolean`.  
  
2. Operador de conversión de ampliación de la clase o estructura que se va a `Boolean?`.  
  
3. Operador de `IsTrue` en la clase o estructura.  
  
4. Conversión de restricción a `Boolean?` que no implica una conversión de `Boolean` a `Boolean?`.  
  
5. Operador de conversión de restricción de la clase o estructura que se va a `Boolean`.  
  
 Si no ha definido ninguna conversión a `Boolean` o a un operador de `IsTrue`, el compilador indicará un error.  
  
> [!NOTE]
> El operador de `IsTrue` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los operadores `IsFalse` y `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)
