---
title: Operador IsTrue
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: bc129d3a3aec76285d5ea8fb727fc72c3064c9cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370653"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue (Operador) (Visual Basic)
Determina si una expresión es `True` .  
  
 No se puede llamar a `IsTrue` explícitamente en el código, pero el compilador de Visual Basic puede utilizarlo para generar código a partir de `OrElse` cláusulas. Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una `OrElse` cláusula, debe definir `IsTrue` en esa clase o estructura.  
  
 El compilador tiene en cuenta los `IsTrue` `IsFalse` operadores y como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilador de IsTrue  
 Cuando haya definido una clase o estructura, puede usar una variable de ese tipo en una `For` `If` instrucción,, `Else If` o `While` , o en una `When` cláusula. Si lo hace, el compilador requiere un operador que convierta el tipo en un `Boolean` valor para que pueda probar una condición. Busca un operador adecuado en el orden siguiente:  
  
1. Un operador de conversión de ampliación de la clase o estructura a `Boolean` .  
  
2. Un operador de conversión de ampliación de la clase o estructura a `Boolean?` .  
  
3. `IsTrue`Operador de la clase o estructura.  
  
4. Una conversión de restricción en `Boolean?` que no implica una conversión de `Boolean` a `Boolean?` .  
  
5. Un operador de conversión de restricción de la clase o estructura a `Boolean` .  
  
 Si no ha definido ninguna conversión a `Boolean` o a un `IsTrue` operador, el compilador indicará un error.  
  
> [!NOTE]
> El `IsTrue` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los `IsFalse` `IsTrue` operadores y.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Consulte también

- [Operador IsFalse](isfalse-operator.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operador OrElse](orelse-operator.md)
