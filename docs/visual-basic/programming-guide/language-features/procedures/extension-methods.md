---
description: 'Más información acerca de: métodos de extensión (Visual Basic)'
title: Métodos de extensión
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 5a1482502b144524c0be90e1c83a38f49b4a4d26
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434360"
---
# <a name="extension-methods-visual-basic"></a>Métodos de extensión (Visual Basic)

Los métodos de extensión permiten a los desarrolladores agregar funcionalidad personalizada a los tipos de datos que ya están definidos sin crear un nuevo tipo derivado. Los métodos de extensión permiten escribir un método al que se puede llamar como si fuera un método de instancia del tipo existente.

## <a name="remarks"></a>Comentarios

Un método de extensión solo puede ser un `Sub` procedimiento o un `Function` procedimiento. No se puede definir una propiedad de extensión, un campo o un evento. Todos los métodos de extensión se deben marcar con el atributo `<Extension>` de extensión del <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres y deben definirse en un [módulo](../../../language-reference/statements/module-statement.md). Si se define un método de extensión fuera de un módulo, el compilador Visual Basic genera el error [BC36551](../../../misc/bc36551.md), "los métodos de extensión solo se pueden definir en módulos".

El primer parámetro de una definición de método de extensión especifica qué tipo de datos extiende el método. Cuando se ejecuta el método, el primer parámetro se enlaza a la instancia del tipo de datos que invoca el método.

El `Extension` atributo solo se puede aplicar a un Visual Basic [`Module`](../../../language-reference/statements/module-statement.md) , [`Sub`](../../../language-reference/statements/sub-statement.md) o [`Function`](../../../language-reference/statements/function-statement.md) . Si se aplica a un objeto o a un objeto `Class` `Structure` , el compilador Visual Basic genera el error [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md), el atributo ' Extension ' solo se puede aplicar a las declaraciones ' module ', ' sub ' o ' function '.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una `Print` extensión para el <xref:System.String> tipo de datos. El método utiliza `Console.WriteLine` para mostrar una cadena. El parámetro del `Print` método, `aString` , establece que el método extiende la <xref:System.String> clase.

[!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]

Observe que la definición del método de extensión está marcada con el atributo de extensión `<Extension()>` . Marcar el módulo en el que se define el método es opcional, pero se debe marcar cada método de extensión. <xref:System.Runtime.CompilerServices> se debe importar para tener acceso al atributo de extensión.

Los métodos de extensión se pueden declarar solo dentro de los módulos. Normalmente, el módulo en el que se define un método de extensión no es el mismo módulo que el en el que se llama. En su lugar, se importa el módulo que contiene el método de extensión, si es necesario, para ponerlo en el ámbito. Después de que el módulo que contiene `Print` está en el ámbito, se puede llamar al método como si fuera un método de instancia normal que no toma ningún argumento, como `ToUpper` :

[!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]

En el ejemplo siguiente, `PrintAndPunctuate` , es también una extensión de <xref:System.String> , esta vez definida con dos parámetros. El primer parámetro, `aString` , establece que el método de extensión extiende <xref:System.String> . El segundo parámetro, `punc` , está pensado para ser una cadena de signos de puntuación que se pasa como argumento cuando se llama al método. El método muestra la cadena seguida de los signos de puntuación.

[!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]

Se llama al método mediante el envío de un argumento de cadena para `punc` : `example.PrintAndPunctuate(".")`

En el ejemplo siguiente se muestra `Print` y se `PrintAndPunctuate` define y se llama a. <xref:System.Runtime.CompilerServices> se importa en el módulo de definición para permitir el acceso al atributo de extensión.

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions

    <Extension()>
    Public Sub Print(aString As String)
        Console.WriteLine(aString)
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module
```

Después, los métodos de extensión se incluyen en el ámbito y se denominan:

```vb
Imports ConsoleApplication2.StringExtensions

Module Module1

    Sub Main()
        Dim example As String = "Example string"
        example.Print()

        example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")
    End Sub
End Module
```

Todo lo que se necesita para poder ejecutar estos métodos de extensión o similares es que están dentro del ámbito. Si el módulo que contiene un método de extensión está en el ámbito, es visible en IntelliSense y se puede llamar como si fuera un método de instancia normal.

Tenga en cuenta que cuando se invocan los métodos, no se envía ningún argumento para el primer parámetro. El parámetro `aString` de las definiciones de método anteriores se enlaza a `example` , la instancia de `String` que los llama. El compilador usará `example` como el argumento enviado al primer parámetro.

Si se llama a un método de extensión para un objeto que se establece en `Nothing` , se ejecuta el método de extensión. Esto no se aplica a los métodos de instancia normales. Puede comprobar explícitamente `Nothing` en el método de extensión.

## <a name="types-that-can-be-extended"></a>Tipos que se pueden extender

Puede definir un método de extensión en la mayoría de los tipos que se pueden representar en una lista de parámetros de Visual Basic, incluidas las siguientes:

- Clases (tipos de referencia)
- Estructuras (tipos de valor)
- Interfaces
- Delegados
- Argumentos ByRef y ByVal
- Parámetros de método genérico
- Matrices

Dado que el primer parámetro especifica el tipo de datos que extiende el método de extensión, es obligatorio y no puede ser opcional. Por ese motivo, `Optional` los parámetros y parámetros `ParamArray` no pueden ser el primer parámetro de la lista de parámetros.

Los métodos de extensión no se consideran en el enlace en tiempo de ejecución. En el ejemplo siguiente, la instrucción `anObject.PrintMe()` genera una <xref:System.MissingMemberException> excepción, la misma excepción que vería si `PrintMe` se eliminara la segunda definición de método de extensión.

[!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]

## <a name="best-practices"></a>Procedimientos recomendados

Los métodos de extensión proporcionan una forma cómoda y eficaz de extender un tipo existente. Sin embargo, para usarlos correctamente, hay que tener en cuenta algunos aspectos. Estas consideraciones se aplican principalmente a los autores de bibliotecas de clases, pero pueden afectar a cualquier aplicación que use métodos de extensión.

En general, los métodos de extensión que se agregan a tipos que no son de su propiedad son más vulnerables que los métodos de extensión agregados a los tipos que usted controla. Se pueden producir varias cosas en las clases que no son de su propiedad y que pueden interferir con los métodos de extensión.

- Si existe un miembro de instancia accesible que tiene una firma que es compatible con los argumentos de la instrucción de llamada, sin conversiones de restricción necesarias del argumento al parámetro, se utilizará el método de instancia en preferencia a cualquier método de extensión. Por lo tanto, si se agrega un método de instancia adecuado a una clase en algún momento, es posible que no se pueda obtener acceso a un miembro de extensión existente del que dependa.

- El autor de un método de extensión no puede impedir que otros programadores escriban métodos de extensión en conflicto que puedan tener prioridad sobre la extensión original.

- Puede mejorar la robustez colocando métodos de extensión en su propio espacio de nombres. Los consumidores de la biblioteca pueden incluir un espacio de nombres o excluirlo, o seleccionar entre espacios de nombres, independientemente del resto de la biblioteca.

- Puede ser más seguro extender las interfaces que para ampliar las clases, especialmente si no posee la interfaz o la clase. Un cambio en una interfaz afecta a cada clase que lo implementa. Por lo tanto, es menos probable que el autor agregue o cambie métodos en una interfaz. Sin embargo, si una clase implementa dos interfaces que tienen métodos de extensión con la misma firma, no hay ningún método de extensión visible.

- Extienda el tipo más específico que pueda. En una jerarquía de tipos, si selecciona un tipo del que se derivan muchos otros tipos, existen capas de posibilidades para la introducción de métodos de instancia u otros métodos de extensión que podrían interferir con el suyo.

## <a name="extension-methods-instance-methods-and-properties"></a>Métodos de extensión, métodos de instancia y propiedades

Cuando un método de instancia en el ámbito tiene una firma que es compatible con los argumentos de una instrucción de llamada, se elige el método de instancia en preferencia a cualquier método de extensión. El método de instancia tiene prioridad incluso si el método de extensión es una coincidencia mejor. En el ejemplo siguiente, `ExampleClass` contiene un método de instancia denominado `ExampleMethod` que tiene un parámetro de tipo `Integer` . El método `ExampleMethod` de extensión extiende `ExampleClass` y tiene un parámetro de tipo `Long` .

[!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]

La primera llamada a `ExampleMethod` en el código siguiente llama al método de extensión, porque `arg1` es `Long` y solo es compatible con el `Long` parámetro en el método de extensión. La segunda llamada a `ExampleMethod` tiene un `Integer` argumento, `arg2` , y llama al método de instancia.

[!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]

Ahora, invierta los tipos de datos de los parámetros en los dos métodos:

[!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]

Esta vez, el código de `Main` llama al método de instancia ambas veces. Esto se debe `arg1` a que y `arg2` tienen una conversión de ampliación a `Long` y el método de instancia tiene prioridad sobre el método de extensión en ambos casos.

[!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]

Por lo tanto, un método de extensión no puede reemplazar un método de instancia existente. Sin embargo, cuando un método de extensión tiene el mismo nombre que un método de instancia pero las firmas no entran en conflicto, se puede tener acceso a ambos métodos. Por ejemplo, si `ExampleClass` la clase contiene un método denominado `ExampleMethod` que no toma ningún argumento, se permiten métodos de extensión con el mismo nombre pero con firmas diferentes, como se muestra en el código siguiente.

[!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]

El resultado de este código es el siguiente:

```console
Extension method
Instance method
```

La situación es más sencilla con las propiedades: Si un método de extensión tiene el mismo nombre que una propiedad de la clase que extiende, el método de extensión no es visible y no se puede tener acceso a él.

## <a name="extension-method-precedence"></a>Precedencia del método de extensión

Cuando dos métodos de extensión que tienen firmas idénticas están en el ámbito y son accesibles, se invocará el que tenga mayor precedencia. La prioridad de un método de extensión se basa en el mecanismo utilizado para poner el método en el ámbito. La lista siguiente muestra la jerarquía de precedencia, de mayor a menor.

1. Métodos de extensión definidos dentro del módulo actual.

2. Métodos de extensión definidos dentro de tipos de datos en el espacio de nombres actual o cualquiera de sus elementos primarios, con espacios de nombres secundarios con mayor precedencia que espacios de nombres primarios.

3. Métodos de extensión definidos dentro de cualquier importación de tipo en el archivo actual.

4. Métodos de extensión definidos dentro de cualquier importación de espacio de nombres en el archivo actual.

5. Métodos de extensión definidos dentro de cualquier importación de tipo de nivel de proyecto.

6. Métodos de extensión definidos dentro de cualquier importación de espacio de nombres de nivel de proyecto.

Si la precedencia no resuelve la ambigüedad, puede usar el nombre completo para especificar el método al que está llamando. Si el `Print` método del ejemplo anterior se define en un módulo denominado `StringExtensions` , el nombre completo es `StringExtensions.Print(example)` en lugar de `example.Print()` .

## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Module (Instrucción)](../../../language-reference/statements/module-statement.md)
- [Argumentos y parámetros de procedimiento](procedure-parameters-and-arguments.md)
- [Parámetros opcionales](optional-parameters.md)
- [Matrices de parámetros](parameter-arrays.md)
- [Información general de atributos](../../concepts/attributes/index.md)
- [Ámbito en Visual Basic](../declared-elements/scope.md)
