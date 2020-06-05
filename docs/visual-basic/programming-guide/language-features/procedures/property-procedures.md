---
title: Procedimientos de propiedad
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: cb5b0e12512e476b7c96bbfb19f8e4f470f6b498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363738"
---
# <a name="property-procedures-visual-basic"></a>Procedimientos de propiedad (Visual Basic)

Un procedimiento de propiedad es una serie de instrucciones Visual Basic que manipulan una propiedad personalizada en un módulo, clase o estructura. Los procedimientos de propiedad también se conocen como *descriptores de acceso de propiedad*.

Visual Basic proporciona para los siguientes procedimientos de propiedad:

- Un `Get` procedimiento devuelve el valor de una propiedad. Se llama cuando se tiene acceso a la propiedad en una expresión.
- Un `Set` procedimiento establece una propiedad en un valor, incluida una referencia de objeto. Se llama al asignar un valor a la propiedad.

Normalmente, los procedimientos de propiedades se definen en pares, mediante las `Get` `Set` instrucciones y, pero se puede definir cualquier procedimiento solo si la propiedad es de solo lectura ([instrucción Get](../../../language-reference/statements/get-statement.md)) o de solo escritura ([instrucción set](../../../language-reference/statements/set-statement.md)).

Puede omitir el `Get` `Set` procedimiento y cuando use una propiedad implementada automáticamente. Para obtener más información, vea [Propiedades implementadas automáticamente](./auto-implemented-properties.md).

Puede definir propiedades en clases, estructuras y módulos. Las propiedades son de `Public` forma predeterminada, lo que significa que puede llamarlas desde cualquier lugar de la aplicación que pueda tener acceso al contenedor de la propiedad.

Para obtener una comparación de propiedades y variables, vea [diferencias entre propiedades y variables en Visual Basic](differences-between-properties-and-variables.md).

## <a name="declaration-syntax"></a>Sintaxis de declaración

Una propiedad se define mediante un bloque de código incluido en la [instrucción Property](../../../language-reference/statements/property-statement.md) y la `End Property` instrucción. Dentro de este bloque, cada procedimiento de propiedad aparece como un bloque interno delimitado por una instrucción de declaración ( `Get` o `Set` ) y la declaración de coincidencia `End` .

La sintaxis para declarar una propiedad y sus procedimientos es la siguiente:

```vb
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]
    [AccessLevel] Get
        ' Statements of the Get procedure.
        ' The following statement returns an expression as the property's value.
        Return Expression
    End Get
    [AccessLevel] Set[(ByVal NewValue As DataType)]
        ' Statements of the Set procedure.
        ' The following statement assigns newvalue as the property's value.
        LValue = NewValue
    End Set
End Property
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

`Modifiers`Puede especificar el nivel de acceso e información relacionada con la sobrecarga, el reemplazo, el uso compartido y el sombreado, así como si la propiedad es de solo lectura o de solo escritura. `AccessLevel`En el `Get` procedimiento o `Set` puede ser cualquier nivel que sea más restrictivo que el nivel de acceso especificado para la propiedad. Para obtener más información, vea [Property Statement](../../../language-reference/statements/property-statement.md).

### <a name="data-type"></a>Tipo de datos

El tipo de datos y el nivel de acceso principal de una propiedad se definen en la `Property` instrucción, no en los procedimientos de propiedad. Una propiedad solo puede tener un tipo de datos. Por ejemplo, no se puede definir una propiedad para almacenar un `Decimal` valor, pero recuperar un `Double` valor.

### <a name="access-level"></a>Nivel de acceso

Sin embargo, puede definir un nivel de acceso principal para una propiedad y restringir aún más el nivel de acceso en uno de sus procedimientos de propiedad. Por ejemplo, puede definir una `Public` propiedad y, a continuación, definir un `Private Set` procedimiento. El `Get` procedimiento sigue siendo `Public` . Puede cambiar el nivel de acceso solo en uno de los procedimientos de una propiedad, y solo puede hacer que sea más restrictivo que el nivel de acceso principal. Para obtener más información, vea [Cómo: declarar una propiedad con niveles de acceso mixtos](how-to-declare-a-property-with-mixed-access-levels.md).

## <a name="parameter-declaration"></a>Declaración de parámetros

Los parámetros se declaran de la misma manera que en los [procedimientos sub](sub-procedures.md), salvo que el mecanismo de paso debe ser `ByVal` .

La sintaxis de cada parámetro de la lista de parámetros es la siguiente:

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración. La sintaxis para especificar un valor predeterminado es la siguiente:

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a>Valor de propiedad

En un `Get` procedimiento, el valor devuelto se proporciona a la expresión de llamada como el valor de la propiedad.

En un `Set` procedimiento, el nuevo valor de la propiedad se pasa al parámetro de la `Set` instrucción. Si declara explícitamente un parámetro, debe declararlo con el mismo tipo de datos que la propiedad. Si no declara un parámetro, el compilador utiliza el parámetro implícito `Value` para representar el nuevo valor que se va a asignar a la propiedad.

## <a name="calling-syntax"></a>Sintaxis de llamada

Un procedimiento de propiedad se invoca implícitamente haciendo referencia a la propiedad. Use el nombre de la propiedad de la misma manera que usaría el nombre de una variable, salvo que debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis. Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.

La sintaxis de una llamada implícita a un `Set` procedimiento es la siguiente:

```vb
propertyname[(argumentlist)] = expression
```

La sintaxis de una llamada implícita a un `Get` procedimiento es la siguiente:

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaration y Call

La siguiente propiedad almacena un nombre completo como dos nombres constituyentes, el nombre y el apellido. Cuando el código de llamada Lee `fullName` , el `Get` procedimiento combina los dos nombres constituyentes y devuelve el nombre completo. Cuando el código de llamada asigna un nuevo nombre completo, el `Set` procedimiento intenta dividirlo en dos nombres constituyentes. Si no encuentra un espacio, lo almacena como el nombre.

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

En el ejemplo siguiente se muestran las llamadas típicas a los procedimientos de propiedad de `fullName` :

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a>Consulte también

- [Procedimientos](index.md)
- [Procedimientos de función](function-procedures.md)
- [Procedimientos de operador](operator-procedures.md)
- [Argumentos y parámetros de procedimiento](procedure-parameters-and-arguments.md)
- [Diferencias entre propiedades y variables en Visual Basic](differences-between-properties-and-variables.md)
- [Procedimiento para crear una propiedad](how-to-create-a-property.md)
- [Procedimiento para llamar a un procedimiento de propiedad](how-to-call-a-property-procedure.md)
- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](how-to-declare-and-call-a-default-property.md)
- [Procedimiento para establecer un valor en una propiedad](how-to-put-a-value-in-a-property.md)
- [Procedimiento para obtener un valor de una propiedad](how-to-get-a-value-from-a-property.md)
