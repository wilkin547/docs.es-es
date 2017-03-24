---
title: "Sobrecargar propiedades y métodos (Visual Basic) | Documentos de Microsoft"
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
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
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
ms.openlocfilehash: 6f379f04ca9b75161baf2bf2c33e87f05a9edf97
ms.lasthandoff: 03/13/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Propiedades y métodos sobrecargados (Visual Basic)
La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumento.  
  
## <a name="overloading-usage"></a>Uso de la sobrecarga  
 La sobrecarga es especialmente útil cuando el modelo de objeto exige el uso de nombres idénticos para procedimientos que operan en diferentes tipos de datos. Por ejemplo, podría tener una clase que puede mostrar diferentes tipos de datos `Display` procedimientos de este aspecto:  
  
 [!code-vb[VbVbalrOOP&#64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 Sin sobrecarga, sería necesario crear distintos nombres para cada procedimiento, aunque lo hacen lo mismo, como se muestra a continuación:  
  
 [!code-vb[VbVbalrOOP&#65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 La sobrecarga facilita la utilice métodos o propiedades porque proporciona una opción de tipos de datos que se puede utilizar. Por ejemplo, sobrecargados `Display` método descrito anteriormente puede llamarse con cualquiera de las siguientes líneas de código:  
  
 [!code-vb[VbVbalrOOP&#66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 En tiempo de ejecución [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama el procedimiento correcto basándose en los tipos de datos de los parámetros especifique.  
  
## <a name="overloading-rules"></a>Reglas de sobrecarga  
 Crear a un miembro sobrecargado para una clase agregando dos o más propiedades o métodos con el mismo nombre. Excepto para los miembros derivados sobrecargados, cada miembro sobrecargado debe tener distintas listas de parámetros y los elementos siguientes no se puede usar como una característica distintiva al sobrecargar una propiedad o un procedimiento:  
  
-   Modificadores, como `ByVal` o `ByRef`, que se aplican a un miembro o parámetros de un miembro.  
  
-   Nombres de parámetros  
  
-   Devolver tipos de procedimientos  
  
 El `Overloads` palabra clave es opcional en la sobrecarga, pero si alguna sobrecarga miembro utiliza la `Overloads` (palabra clave) y, a continuación, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.  
  
 Las clases derivadas pueden sobrecargar miembros heredados con miembros que tengan idénticos parámetros y tipos de parámetros, un proceso conocido como *sombrear por nombre y firma*. Si el `Overloads` se utiliza la palabra clave al sombrear por nombre y firma, se utilizará la implementación de la clase derivada del miembro en lugar de la implementación de la clase base y todas las demás sobrecargas de dicho miembro estarán disponibles para las instancias de la clase derivada.  
  
 Si el `Overloads` se omite la palabra clave al sobrecargar un miembro heredado con un miembro que tiene parámetros y tipos de parámetros idénticos, a continuación, la sobrecarga se denomina *sombrear por nombre*. Sombrear por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas disponibles para las instancias de la clase derivada y sus descendientes.  
  
 El `Overloads` y `Shadows` modificadores no pueden utilizarse con la misma propiedad o método.  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea métodos sobrecargados que aceptan un `String` o `Decimal` representación de una cantidad en dólares y devuelven una cadena que contiene los impuestos.  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Para utilizar este ejemplo para crear un método sobrecargado  
  
1.  Abra un nuevo proyecto y agregue una clase denominada `TaxClass`.  
  
2.  Agregue el código siguiente a la clase `TaxClass`.  
  
     [!code-vb[VbVbalrOOP&#67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  Agregue el siguiente procedimiento para el formulario.  
  
     [!code-vb[VbVbalrOOP&#68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  Agregar un botón a su formulario y llame a la `ShowTax` procedimiento desde el `Button1_Click` eventos del botón.  
  
5.  Ejecute el proyecto y haga clic en el botón del formulario para probar sobrecargado `ShowTax` procedimiento.  
  
 En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincida con los parámetros utilizados. Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje, "Price is a String. Impuestos es $5.12" se muestra. `TaxAmount`se llama con un `Decimal` valor de la segunda vez y el mensaje, "Price is a Decimal. Impuestos es $5.12" se muestra.  
  
## <a name="see-also"></a>Vea también  
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Sombras](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)   
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)   
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
