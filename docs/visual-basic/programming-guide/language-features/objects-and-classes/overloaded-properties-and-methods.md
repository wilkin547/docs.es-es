---
title: "Propiedades y m&#233;todos sobrecargados (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases [Visual Basic], métodos"
  - "clases [Visual Basic], propiedades"
  - "sobrecarga de métodos"
  - "métodos [Visual Basic], sobrecargar"
  - "nombres, varios procedimientos con el mismo"
  - "Overloads (palabra clave), miembros sobrecargados"
  - "procedimientos, varios con el mismo nombre"
  - "propiedades [Visual Basic], sobrecargar"
  - "sombrear"
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Propiedades y m&#233;todos sobrecargados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La sobrecarga consiste en crear más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre y distintos tipos de argumento.  
  
## Uso de la sobrecarga  
 La sobrecarga es especialmente útil cuando un modelo de objeto exige el uso de nombres idénticos para procedimientos que operan en diferentes tipos de datos.  Por ejemplo, una clase que puede mostrar diferentes tipos de datos podría tener procedimientos `Display` como los siguientes:  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 Sin sobrecarga, sería necesario crear distintos nombres para cada procedimiento, aunque realicen el mismo cometido, como se muestra a continuación:  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 La sobrecarga facilita el uso de propiedades o métodos, puesto que ofrece una selección de tipos de datos que se pueden utilizar.  Por ejemplo, se pude llamar al método sobrecargado `Display` descrito anteriormente con cualquiera de las siguientes líneas de código:  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 En tiempo de ejecución, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] llama al procedimiento correcto basándose en los tipos de datos de los parámetros que se han especificado.  
  
## Reglas de sobrecarga  
 Es posible crear un miembro sobrecargado para una clase agregando dos o más propiedades o métodos con el mismo nombre.  A excepción de los miembros derivados sobrecargados, cada miembro sobrecargado debe tener distintas listas de parámetros, y los elementos que a continuación se enumeran, no se pueden utilizar como características diferenciadoras al sobrecargar una propiedad o un procedimiento:  
  
-   Modificadores, como por ejemplo `ByVal` o `ByRef`, que se aplican a un miembro o parámetros de un miembro.  
  
-   Nombres de parámetros  
  
-   Tipos de valores devueltos de procedimientos  
  
 La palabra clave `Overloads` es opcional en la sobrecarga, aunque si algún miembro sobrecargado la utiliza, todos los demás miembros sobrecargados con el mismo nombre deben especificarla también.  
  
 Las clases derivadas pueden sobrecargar miembros heredados con miembros que tengan idénticos parámetros y tipos de parámetros, un proceso denominado *sombrear por nombre y firma*.  Si se utiliza la palabra clave `Overloads` al sombrear por nombre y firma, se utilizará la implementación de la clase derivada del miembro en vez de la implementación de la clase base y todas las demás sobrecargas de dicho miembro estarán disponibles para las instancias de la clase derivada.  
  
 Si se omite la palabra clave `Overloads` al sobrecargar un miembro heredado con un miembro que tiene parámetros y tipos de parámetros idénticos, la sobrecarga se denomina *sombrear por nombre*.  El proceso sombrear por nombre reemplaza a la implementación heredada de un miembro y hace que todas las demás sobrecargas no estén disponibles para las instancias de la clase derivada y sus descendientes.  
  
 Los modificadores `Overloads` y `Shadows` no pueden utilizarse a la vez con la misma propiedad o método.  
  
### Ejemplo  
 El ejemplo siguiente crea métodos sobrecargados que aceptan una representación `String` o `Decimal` de una cantidad en dólares y devuelven una cadena que contiene los impuestos sobre ventas.  
  
##### Para utilizar este ejemplo para crear un método sobrecargado  
  
1.  Abra un nuevo proyecto y agregue una clase denominada `TaxClass`.  
  
2.  Agregue el código siguiente a la clase `TaxClass`.  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  Agregue el procedimiento siguiente a su formulario.  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  Agregue un botón al formulario y llame al procedimiento `ShowTax` desde el evento `Button1_Click` del botón.  
  
5.  Ejecute el proyecto y haga clic en el botón del formulario para probar el procedimiento sobrecargado `ShowTax`.  
  
 En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincida con los parámetros que se utilicen.  Al hacer clic en el botón, primero se llama al método sobrecargado con un parámetro `Price` que es una cadena y se muestra el mensaje: "Price is a String.  Tax is $5.12".  La segunda vez, se llama a `TaxAmount` con un valor `Decimal` y se muestra el mensaje, "Price is a Decimal.  Tax is $5.12".  
  
## Vea también  
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)   
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)