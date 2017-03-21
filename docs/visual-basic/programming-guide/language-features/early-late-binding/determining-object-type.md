---
title: Determinar el tipo de objeto (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2486d989801fc4866a50747aa963b509a627994d
ms.lasthandoff: 03/13/2017

---
# <a name="determining-object-type-visual-basic"></a>Determinar tipos de objeto (Visual Basic)
Variables de objeto genéricas (es decir, variables declaradas como `Object`) puede contener objetos de cualquier clase. Cuando se utilizan variables de tipo `Object`, puede que necesite realizar diferentes acciones basadas en la clase del objeto; por ejemplo, algunos objetos podrían no admitir una determinada propiedad o método. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]proporciona dos maneras de determinar qué tipo de objeto se almacena en una variable de objeto: la `TypeName` (función) y `TypeOf...Is` (operador).  
  
## <a name="typename-and-typeofis"></a>TypeName y TypeOf... Es  
 El `TypeName` función devuelve una cadena y es la mejor opción cuando necesite almacenar o mostrar el nombre de clase de un objeto, como se muestra en el siguiente fragmento de código:  
  
 [!code-vb[VbVbalrOOP&#92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 El `TypeOf...Is` operador es la mejor opción para comprobar el tipo de un objeto, porque es mucho más rápido que una comparación de cadena equivalente mediante `TypeName`. El siguiente fragmento de código utiliza `TypeOf...Is` dentro de un `If...Then...Else` instrucción:  
  
 [!code-vb[VbVbalrOOP&#93;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Aquí vence una palabra de advertencia. El `TypeOf...Is` operador devuelve `True` si un objeto es de un tipo específico, o se deriva de un tipo específico. Casi todo lo que haga con [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] implica objetos, que incluyen algunos elementos que normalmente no se suponen objetos, por ejemplo, cadenas y enteros. Estos objetos se derivan y heredan métodos de <xref:System.Object>.</xref:System.Object> Cuando se pasa un `Integer` y evaluada con `Object`, `TypeOf...Is` operador devuelve `True`. En el ejemplo siguiente se notifica que el parámetro `InParam` es una `Object` y `Integer`:  
  
 [!code-vb[VbVbalrOOP&#94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 En el ejemplo siguiente se utiliza tanto `TypeOf...Is` y `TypeName` para determinar el tipo de objeto que se pasa en el `Ctrl` argumento. El `TestObject` las llamadas a procedimiento `ShowType` con tres tipos diferentes de controles.  
  
#### <a name="to-run-the-example"></a>Para ejecutar el ejemplo  
  
1.  Cree un nuevo proyecto de aplicación para Windows y agregue un <xref:System.Windows.Forms.Button>(control), un <xref:System.Windows.Forms.CheckBox>control y un <xref:System.Windows.Forms.RadioButton>control al formulario.</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button>  
  
2.  En el botón en el formulario, llame a la `TestObject` procedimiento.  
  
3.  Agregue el código siguiente al formulario:  
  
     [!code-vb[VbVbalrOOP&#95;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A>   
 [Llamar a una propiedad o método mediante un nombre de cadena](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)   
 [Tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [If... Entonces... Else (instrucción)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Tipo de datos de cadena](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Integer (tipo de datos)](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
