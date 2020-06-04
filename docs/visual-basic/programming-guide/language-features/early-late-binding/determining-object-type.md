---
title: Determinación del tipo de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 3b1c4ad0ab4fd8d2897aff6ad9097cdc81272455
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410649"
---
# <a name="determining-object-type-visual-basic"></a>Determinar tipos de objeto (Visual Basic)
Las variables de objeto genérico (es decir, las variables que se declaran como `Object` ) pueden contener objetos de cualquier clase. Al usar variables de tipo `Object` , es posible que necesite realizar diferentes acciones en función de la clase del objeto; por ejemplo, algunos objetos podrían no admitir una propiedad o un método determinados. Visual Basic proporciona dos formas de determinar qué tipo de objeto se almacena en una variable de objeto: la `TypeName` función y el `TypeOf...Is` operador.  
  
## <a name="typename-and-typeofis"></a>TypeName y typeof... Encuentra  
 La `TypeName` función devuelve una cadena y es la mejor opción cuando necesita almacenar o mostrar el nombre de clase de un objeto, tal y como se muestra en el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 El `TypeOf...Is` operador es la mejor opción para probar el tipo de un objeto, ya que es mucho más rápido que una comparación de cadenas equivalente mediante `TypeName` . En el fragmento de código siguiente se usa `TypeOf...Is` dentro de una `If...Then...Else` instrucción:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Aquí se debe tener precaución. El `TypeOf...Is` operador devuelve `True` si un objeto es de un tipo específico o se deriva de un tipo específico. Casi todo lo que se hace con Visual Basic implica objetos, que incluyen algunos elementos que normalmente no se consideran objetos como, por ejemplo, cadenas y enteros. Estos objetos se derivan de los métodos y heredan de <xref:System.Object> . Cuando se pasa `Integer` y se evalúa con `Object` , el `TypeOf...Is` operador devuelve `True` . En el ejemplo siguiente se informa de que el parámetro `InParam` es un `Object` y un `Integer` :  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 En el ejemplo siguiente se usan `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se le ha pasado en el `Ctrl` argumento. El `TestObject` procedimiento llama a `ShowType` con tres tipos diferentes de controles.  
  
#### <a name="to-run-the-example"></a>Para ejecutar el ejemplo  
  
1. Cree un nuevo proyecto de aplicación para Windows y agregue un control <xref:System.Windows.Forms.Button> , un <xref:System.Windows.Forms.CheckBox> control y un <xref:System.Windows.Forms.RadioButton> control al formulario.  
  
2. En el botón del formulario, llame al `TestObject` procedimiento.  
  
3. Agregue el código siguiente al formulario:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Llamar a una propiedad o método mediante un nombre de cadena](calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Instrucción If...Then...Else](../../../language-reference/statements/if-then-else-statement.md)
- [String (Tipo de datos)](../../../language-reference/data-types/string-data-type.md)
- [Tipo de datos Integer](../../../language-reference/data-types/integer-data-type.md)
