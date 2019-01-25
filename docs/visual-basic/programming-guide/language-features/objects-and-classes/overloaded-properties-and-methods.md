---
title: Propiedades sobrecargadas y métodos (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 472cd0dbfc0544477d8e368b553a454b977d633c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498614"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Propiedades sobrecargadas y métodos (Visual Basic)

La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumento.  
  
## <a name="overloading-usage"></a>Uso de la sobrecarga

 Sobrecarga es especialmente útil cuando el modelo de objeto exige el uso de nombres idénticos para los procedimientos que operan en distintos tipos de datos. Por ejemplo, podría tener una clase que puede mostrar diferentes tipos de datos `Display` procedimientos que tienen un aspecto similar al siguiente:  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 Sin sobrecarga, sería necesario crear nombres distintos para cada procedimiento, aunque lo hacen lo mismo, tal como se muestra a continuación:  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 Sobrecarga hace más fácil de usar los métodos o propiedades porque proporciona una opción de tipos de datos que se puede usar. Por ejemplo, el sobrecargado `Display` método descrito anteriormente se puede llamar con cualquiera de las siguientes líneas de código:  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 En tiempo de ejecución, Visual Basic llama al procedimiento correcto basándose en los tipos de datos de los parámetros especificados.  
  
## <a name="overloading-rules"></a>Reglas de sobrecarga

 Crear a un miembro sobrecargado para una clase mediante la adición de dos o más propiedades o métodos con el mismo nombre. Excepto para los miembros derivados sobrecargados, cada miembro sobrecargado debe tener distintas listas de parámetros y los elementos siguientes no se puede usar como una característica distintiva cuando sobrecargue un procedimiento o propiedad:  
  
-   Modificadores, como `ByVal` o `ByRef`, que se aplican a un miembro o los parámetros del miembro.  
  
-   Nombres de parámetros  
  
-   Tipos de valor devuelto de procedimientos  
  
 El `Overloads` palabra clave es opcional cuando sobrecargue un procedimiento, pero si alguna sobrecarga miembro usa la `Overloads` palabra clave y, a continuación, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.  
  
 Las clases derivadas pueden sobrecargar los miembros heredados con miembros que tienen parámetros idénticos y los tipos de parámetro, un proceso conocido como *sombrear por nombre y firma*. Si el `Overloads` palabra clave se usa cuando el sombreado por nombre y firma, implementación de la clase derivada del miembro se usará en lugar de la implementación de la clase base y todas las demás sobrecargas para ese miembro estará disponibles para las instancias de la clase derivada.  
  
 Si el `Overloads` se omite la palabra clave cuando sobrecargue un miembro heredado con un miembro que tiene parámetros y tipos de parámetro idénticos, a continuación, la sobrecarga se denomina *sombrear por nombre*. Sombrear por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas que no están disponibles para las instancias de la clase derivada y sus descendientes.  
  
 El `Overloads` y `Shadows` modificadores no pueden utilizarse con la misma propiedad o método.  
  
### <a name="example"></a>Ejemplo

 En el ejemplo siguiente se crea métodos sobrecargados que aceptan un `String` o `Decimal` representación de una cantidad en dólares y devuelven una cadena que contiene los impuestos.  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Para usar este ejemplo para crear un método sobrecargado
  
1.  Abra un nuevo proyecto y agregue una clase denominada `TaxClass`.  
  
2.  Agregue el código siguiente a la clase `TaxClass` .  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  Agregue el siguiente procedimiento para el formulario.  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  Agregar un botón a su formulario y llame a la `ShowTax` procedimiento desde el `Button1_Click` eventos del botón.  
  
5.  Ejecute el proyecto y haga clic en el botón del formulario para probar sobrecargado `ShowTax` procedimiento.  
  
 En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincida con los parámetros que se va a usar. Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje, "precio es una cadena. Impuestos es $5.12" se muestra. `TaxAmount` se llama con un `Decimal` valor de la segunda vez y el mensaje, "precio es un Decimal. Impuestos es $5.12" se muestra.  
  
## <a name="see-also"></a>Vea también

- [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)
- [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)
- [Sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
