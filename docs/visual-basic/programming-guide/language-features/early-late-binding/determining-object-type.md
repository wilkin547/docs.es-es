---
title: Determinar tipos de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 4014bef2e0c27a0f6a684bc1ed95019f392062a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050524"
---
# <a name="determining-object-type-visual-basic"></a>Determinar tipos de objeto (Visual Basic)
Variables de objeto genéricas (es decir, las variables se declaran como `Object`) puede contener objetos de cualquier clase. Al usar las variables de tipo `Object`, es posible que deba realizar diferentes acciones basadas en la clase del objeto; por ejemplo, algunos objetos podrían no admitir un método o propiedad concreta. Visual Basic ofrece dos maneras de determinar qué tipo de objeto se almacena en una variable de objeto: el `TypeName` función y el `TypeOf...Is` operador.  
  
## <a name="typename-and-typeofis"></a>TypeName y TypeOf... Es  
 El `TypeName` función devuelve una cadena y es la mejor opción cuando necesite almacenar o mostrar el nombre de clase de un objeto, como se muestra en el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 El `TypeOf...Is` operador es la mejor opción para comprobar el tipo de un objeto, porque es mucho más rápido que una comparación de cadena equivalente mediante `TypeName`. El siguiente fragmento de código utiliza `TypeOf...Is` dentro de un `If...Then...Else` instrucción:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Aquí vence una palabra de advertencia. El `TypeOf...Is` operador devuelve `True` si un objeto es de un tipo específico, o se deriva de un tipo específico. Casi todo lo que hace con Visual Basic implica objetos, que incluyen algunos elementos que normalmente no se considera objetos, como cadenas y enteros. Estos objetos se derivan y heredan los métodos de <xref:System.Object>. Cuando se pasa un `Integer` y evaluado con `Object`, `TypeOf...Is` operador devuelve `True`. En el ejemplo siguiente se notifica que el parámetro `InParam` es tanto un `Object` y un `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 En el ejemplo siguiente se usa tanto `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se pasa en el `Ctrl` argumento. El `TestObject` las llamadas a procedimiento `ShowType` con tres tipos diferentes de controles.  
  
#### <a name="to-run-the-example"></a>Para ejecutar el ejemplo  
  
1. Cree un nuevo proyecto de aplicación de Windows y agregue un <xref:System.Windows.Forms.Button> (control), un <xref:System.Windows.Forms.CheckBox> control y un <xref:System.Windows.Forms.RadioButton> control al formulario.  
  
2. En el botón en el formulario, llame a la `TestObject` procedimiento.  
  
3. Agregue el código siguiente al formulario:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Llamada a una propiedad o método mediante un nombre de cadena](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [If...Then...Else (instrucción)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [String (tipo de datos)](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Integer (tipo de datos)](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
