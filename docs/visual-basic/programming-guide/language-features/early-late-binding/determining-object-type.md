---
title: Determinar el tipo de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: a77cc0603a0b61f58a4aa703c4b1e6ef4c26729c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345198"
---
# <a name="determining-object-type-visual-basic"></a>Determinar tipos de objeto (Visual Basic)
Las variables de objeto genéricas (es decir, las variables que se declaran como `Object`) pueden contener objetos de cualquier clase. Al usar variables de tipo `Object`, es posible que necesite realizar diferentes acciones en función de la clase del objeto. por ejemplo, es posible que algunos objetos no admitan una propiedad o un método determinados. Visual Basic proporciona dos formas de determinar qué tipo de objeto se almacena en una variable de objeto: la función `TypeName` y el operador `TypeOf...Is`.  
  
## <a name="typename-and-typeofis"></a>TypeName y typeof... Encuentra  
 La función `TypeName` devuelve una cadena y es la mejor opción cuando necesita almacenar o mostrar el nombre de clase de un objeto, como se muestra en el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 El operador `TypeOf...Is` es la mejor opción para probar el tipo de un objeto, ya que es mucho más rápido que una comparación de cadenas equivalente mediante `TypeName`. En el siguiente fragmento de código se usa `TypeOf...Is` dentro de una instrucción de `If...Then...Else`:  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 Aquí se debe tener precaución. El operador `TypeOf...Is` devuelve `True` si un objeto es de un tipo específico o se deriva de un tipo específico. Casi todo lo que se hace con Visual Basic implica objetos, que incluyen algunos elementos que normalmente no se consideran objetos como, por ejemplo, cadenas y enteros. Estos objetos se derivan de los métodos y heredan de <xref:System.Object>. Cuando se pasa un `Integer` y se evalúa con `Object`, el operador de `TypeOf...Is` devuelve `True`. En el ejemplo siguiente se informa de que el parámetro `InParam` es tanto un `Object` como un `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 En el ejemplo siguiente se usan `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se le ha pasado en el argumento `Ctrl`. El procedimiento `TestObject` llama a `ShowType` con tres tipos diferentes de controles.  
  
#### <a name="to-run-the-example"></a>Para ejecutar el ejemplo  
  
1. Cree un nuevo proyecto de aplicación para Windows y agregue un control de <xref:System.Windows.Forms.Button>, un control de <xref:System.Windows.Forms.CheckBox> y un control de <xref:System.Windows.Forms.RadioButton> al formulario.  
  
2. En el botón del formulario, llame al procedimiento `TestObject`.  
  
3. Agregue el código siguiente al formulario:  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [Llamada a una propiedad o método mediante un nombre de cadena](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [If...Then...Else (instrucción)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [String (tipo de datos)](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Integer (tipo de datos)](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
