---
title: "Propiedades y métodos sobrecargados (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a872540716941ccd0dbb8b058508b89ce26a988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Propiedades y métodos sobrecargados (Visual Basic)
La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumento.  
  
## <a name="overloading-usage"></a>Uso de la sobrecarga  
 La sobrecarga es especialmente útil cuando el modelo de objeto exige el uso de nombres idénticos para procedimientos que operan en diferentes tipos de datos. Por ejemplo, podría tener una clase que puede mostrar varios tipos de datos diferentes `Display` procedimientos que tengan un aspecto similar al siguiente:  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 Sin sobrecarga, sería necesario crear nombres distintos para cada procedimiento, aunque lo hacen lo mismo, tal y como se muestra a continuación:  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 Sobrecarga resulta más fácil utilizar los métodos o propiedades porque proporciona una opción de tipos de datos que se puede usar. Por ejemplo, sobrecargado `Display` método descrito anteriormente puede llamarse con cualquiera de las siguientes líneas de código:  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 En tiempo de ejecución [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] llama el procedimiento correcto basándose en los tipos de datos de los parámetros especifique.  
  
## <a name="overloading-rules"></a>Reglas de sobrecarga  
 Crear a un miembro sobrecargado para una clase agregando dos o más propiedades o métodos con el mismo nombre. Excepto para los miembros derivados sobrecargados, cada miembro sobrecargado debe tener distintas listas de parámetros y los elementos siguientes no se puede usar como una característica distintiva al sobrecargar una propiedad o procedimiento:  
  
-   Modificadores, como `ByVal` o `ByRef`, que se aplican a un miembro o parámetros del miembro.  
  
-   Nombres de parámetros  
  
-   Tipos de valor devueltos de procedimientos  
  
 El `Overloads` palabra clave es opcional cuando sobrecargue un procedimiento, pero si alguna sobrecarga miembro usa la `Overloads` palabra clave y, a continuación, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.  
  
 Las clases derivadas pueden sobrecargar los miembros heredados con miembros que tengan idénticos parámetros y tipos de parámetros, un proceso conocido como *sombrear por nombre y firma*. Si el `Overloads` se utiliza la palabra clave cuando sombrear por nombre y firma, implementación de la clase derivada del miembro se usará en lugar de la implementación de la clase base y todas las demás sobrecargas de dicho miembro estarán disponibles para instancias de la clase derivada.  
  
 Si el `Overloads` se omite la palabra clave al sobrecargar un miembro heredado con un miembro que tiene parámetros y tipos de parámetro idénticos, a continuación, la sobrecarga se denomina *sombrear por nombre*. Sombrear por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas disponibles para las instancias de la clase derivada y sus descendientes.  
  
 El `Overloads` y `Shadows` modificadores no pueden utilizarse con la misma propiedad o método.  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea métodos sobrecargados que aceptan un `String` o `Decimal` representación de una cantidad en dólares y devuelven una cadena que contiene los impuestos.  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Para usar este ejemplo para crear un método sobrecargado  
  
1.  Abra un nuevo proyecto y agregue una clase denominada `TaxClass`.  
  
2.  Agregue el código siguiente a la clase `TaxClass`.  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  Agregue el siguiente procedimiento para el formulario.  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  Agregar un botón a su formulario y llame a la `ShowTax` procedimiento desde la `Button1_Click` eventos del botón.  
  
5.  Ejecute el proyecto y haga clic en el botón del formulario para probar sobrecargado `ShowTax` procedimiento.  
  
 En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincida con los parámetros que se va a usar. Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje, "precio es una cadena. Impuestos es $5.12" se muestra. `TaxAmount`se llama con un `Decimal` valor de la segunda vez y el mensaje, "Price is a Decimal. Impuestos es $5.12" se muestra.  
  
## <a name="see-also"></a>Vea también  
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
