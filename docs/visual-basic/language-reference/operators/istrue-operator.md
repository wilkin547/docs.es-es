---
title: IsTrue (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 1152f4b512a85ae183f8fc8d476b69685e2926ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966917"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue (Operador) (Visual Basic)
Determina si una expresión es `True`.  
  
 No se puede `IsTrue` llamar a explícitamente en el código, pero el compilador de Visual Basic puede `OrElse` utilizarlo para generar código a partir de cláusulas. Si define una clase o estructura y, a continuación, usa una variable de ese tipo `OrElse` en una cláusula, debe `IsTrue` definir en esa clase o estructura.  
  
 El compilador `IsTrue` tiene `IsFalse` en cuenta los operadores y como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilador de IsTrue  
 Cuando haya definido una clase o estructura, puede usar una variable de `For`ese tipo en una instrucción, `If`, `Else If`o `While` , o en una `When` cláusula. Si lo hace, el compilador requiere un operador que convierta el tipo en `Boolean` un valor para que pueda probar una condición. Busca un operador adecuado en el orden siguiente:  
  
1. Un operador de conversión de ampliación de la clase o estructura `Boolean`a.  
  
2. Un operador de conversión de ampliación de la clase o estructura `Boolean?`a.  
  
3. `IsTrue` Operador de la clase o estructura.  
  
4. Una conversión de restricción en `Boolean?` que no implica una conversión de `Boolean` a `Boolean?`.  
  
5. Un operador de conversión de restricción de la clase o estructura `Boolean`a.  
  
 Si no ha definido ninguna conversión a o `Boolean` a un `IsTrue` operador, el compilador indicará un error.  
  
> [!NOTE]
> El `IsTrue` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el contorno de una estructura que `IsFalse` incluye `IsTrue` definiciones para los operadores y.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)
