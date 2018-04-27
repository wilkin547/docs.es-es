---
title: Determinar tipos de objeto (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6d24be68ea4a9872f8f4fe89c1aabb943fbcb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="determining-object-type-visual-basic"></a>Determinar tipos de objeto (Visual Basic)
Variables de objeto genéricas (es decir, las variables se declara como `Object`) puede contener objetos de cualquier clase. Al usar las variables de tipo `Object`, puede que necesite realizar diferentes acciones basadas en la clase del objeto; por ejemplo, algunos objetos podrían no admitir un método o propiedad determinado. Visual Basic proporciona dos formas de determinar qué tipo de objeto se almacena en una variable de objeto: la `TypeName` función y el `TypeOf...Is` operador.  
  
## <a name="typename-and-typeofis"></a>TypeName y TypeOf... Es  
 El `TypeName` función devuelve una cadena y es la mejor opción cuando necesite almacenar o mostrar el nombre de clase de un objeto, como se muestra en el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 El `TypeOf...Is` operador es la mejor opción para comprobar el tipo de un objeto, porque es mucho más rápido que una comparación de cadena equivalente mediante `TypeName`. En el fragmento de código siguiente se utiliza `TypeOf...Is` dentro de un `If...Then...Else` instrucción:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Una palabra de precaución aquí es debida. El `TypeOf...Is` operador devuelve `True` si un objeto es de un tipo específico, o se deriva de un tipo específico. Casi todo lo que haga con Visual Basic incluye objetos, que incluyen algunos elementos que normalmente no se suponen como objetos, como cadenas y números enteros. Estos objetos se derivan y heredan métodos de <xref:System.Object>. Cuando se pasa un `Integer` y evaluado con `Object`, `TypeOf...Is` operador devuelve `True`. En el ejemplo siguiente se notifica que el parámetro `InParam` es tanto un `Object` y `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 En el ejemplo siguiente se utiliza tanto `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se pasa en el `Ctrl` argumento. El `TestObject` las llamadas a procedimiento `ShowType` con tres tipos diferentes de controles.  
  
#### <a name="to-run-the-example"></a>Para ejecutar el ejemplo  
  
1.  Cree un nuevo proyecto de aplicación para Windows y agregue un <xref:System.Windows.Forms.Button> (control), un <xref:System.Windows.Forms.CheckBox> (control) y un <xref:System.Windows.Forms.RadioButton> control al formulario.  
  
2.  En el botón en el formulario, llame a la `TestObject` procedimiento.  
  
3.  Agregue el código siguiente al formulario:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [Llamada a una propiedad o método mediante un nombre de cadena](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [If...Then...Else (instrucción)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [String (tipo de datos)](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Integer (tipo de datos)](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
