---
title: Propiedades y métodos sobrecargados
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: 1672f12773ece012c580253b6dafbf9d0ac8f07c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389157"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Propiedades y métodos sobrecargados (Visual Basic)

La sobrecarga es la creación de más de un procedimiento, constructor de instancia o propiedad en una clase con el mismo nombre pero con distintos tipos de argumentos.

## <a name="overloading-usage"></a>Sobrecarga del uso

La sobrecarga es especialmente útil cuando el modelo de objetos determina que se emplean nombres idénticos para los procedimientos que operan en tipos de datos diferentes. Por ejemplo, una clase que puede mostrar varios tipos de datos diferentes podría tener `Display` procedimientos que tienen el siguiente aspecto:

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

Sin sobrecarga, tendría que crear nombres distintos para cada procedimiento, aunque hagan lo mismo, como se muestra a continuación:

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

La sobrecarga facilita el uso de propiedades o métodos, ya que proporciona una selección de tipos de datos que se pueden usar. Por ejemplo, `Display` se puede llamar al método sobrecargado descrito anteriormente con cualquiera de las siguientes líneas de código:

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

En tiempo de ejecución, Visual Basic llama al procedimiento correcto en función de los tipos de datos de los parámetros que se especifiquen.

## <a name="overloading-rules"></a>Sobrecargar reglas

 Puede crear un miembro sobrecargado para una clase agregando dos o más propiedades o métodos con el mismo nombre. A excepción de los miembros derivados sobrecargados, cada miembro sobrecargado debe tener listas de parámetros diferentes y los elementos siguientes no se pueden usar como una característica diferenciada al sobrecargar una propiedad o un procedimiento:

- Modificadores, como `ByVal` o `ByRef` , que se aplican a un miembro o a los parámetros del miembro.

- Nombres de parámetros

- Tipos devueltos de procedimientos

La `Overloads` palabra clave es opcional al sobrecargar, pero si cualquier miembro sobrecargado utiliza la `Overloads` palabra clave, todos los demás miembros sobrecargados con el mismo nombre también deben especificar esta palabra clave.

Las clases derivadas pueden sobrecargar los miembros heredados con miembros que tienen parámetros y tipos de parámetro idénticos, un proceso conocido como *sombreado por nombre y firma*. Si `Overloads` se usa la palabra clave al sombrear por nombre y firma, se usará la implementación de la clase derivada del miembro en lugar de la implementación en la clase base, y todas las demás sobrecargas para ese miembro estarán disponibles para las instancias de la clase derivada.

Si `Overloads` se omite la palabra clave al sobrecargar un miembro heredado con un miembro que tiene parámetros y tipos de parámetro idénticos, la sobrecarga se denomina *sombreado por nombre*. El sombreado por nombre reemplaza la implementación heredada de un miembro y hace que todas las demás sobrecargas no estén disponibles para las instancias de la clase derivada y su decedents.

Los `Overloads` `Shadows` modificadores y no se pueden usar con la misma propiedad o método.

### <a name="example"></a>Ejemplo

En el ejemplo siguiente se crean métodos sobrecargados que aceptan `String` una `Decimal` representación o de una cantidad de dólares y devuelven una cadena que contiene el impuesto de ventas.

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Para usar este ejemplo para crear un método sobrecargado

1. Abra un nuevo proyecto y agregue una clase denominada `TaxClass` .

2. Agregue el siguiente código a la clase `TaxClass` .

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. Agregue el procedimiento siguiente al formulario.

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. Agregue un botón al formulario y llame al `ShowTax` procedimiento desde el `Button1_Click` evento del botón.

5. Ejecute el proyecto y haga clic en el botón del formulario para probar el procedimiento sobrecargado `ShowTax` .

En tiempo de ejecución, el compilador elige la función sobrecargada adecuada que coincide con los parámetros que se usan. Al hacer clic en el botón, se llama primero al método sobrecargado con un `Price` parámetro que es una cadena y el mensaje, "Price Is a String. Tax es $5,12. `TaxAmount`se llama a con un `Decimal` valor la segunda vez y el mensaje, "Price es un decimal. Tax es $5,12.

## <a name="see-also"></a>Consulte también

- [Objetos y clases](index.md)
- [Sombrear en Visual Basic](../declared-elements/shadowing.md)
- [Instrucción Sub](../../../language-reference/statements/sub-statement.md)
- [Fundamentos de la herencia](inheritance-basics.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [ByVal](../../../language-reference/modifiers/byval.md)
- [ByRef](../../../language-reference/modifiers/byref.md)
- [Sobrecargas](../../../language-reference/modifiers/overloads.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
