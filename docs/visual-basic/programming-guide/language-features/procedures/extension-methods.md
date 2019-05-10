---
title: Métodos de extensión (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 48a2609a1931e55d24d98cd2b336fc16c520c948
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649637"
---
# <a name="extension-methods-visual-basic"></a>Métodos de extensión (Visual Basic)
Métodos de extensión permiten a los desarrolladores agregar funcionalidad personalizada a los tipos de datos que ya están definidos sin crear un nuevo tipo derivado. Métodos de extensión permiten escribir un método que se pueda llamar como si fuera un método de instancia del tipo existente.  
  
## <a name="remarks"></a>Comentarios  
 Un método de extensión solo puede ser un `Sub` procedimiento o un `Function` procedimiento. No se puede definir una propiedad de extensión, campo o evento. Todos los métodos de extensión se deben marcar con el atributo de extensión `<Extension()>` desde el <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres.  
  
 El primer parámetro en una definición de método de extensión especifica qué tipo de datos extiende el método. Cuando se ejecuta el método, el primer parámetro se enlaza a la instancia del tipo de datos que invoca el método.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se define un `Print` extensión a la <xref:System.String> tipo de datos. Usa el método `Console.WriteLine` para mostrar una cadena. El parámetro de la `Print` método `aString`, Establece que el método extiende la <xref:System.String> clase.  
  
 [!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]  
  
 Tenga en cuenta que la definición del método de extensión se marca con el atributo de extensión `<Extension()>`. Marcar el módulo en el que se define el método es opcional, pero se debe marcar cada método de extensión. <xref:System.Runtime.CompilerServices> debe importarse con el fin de obtener acceso al atributo de extensión.  
  
 Métodos de extensión se pueden declarar únicamente dentro de los módulos. Normalmente, el módulo en el que se define un método de extensión no es el mismo módulo que lo en el que se llama. En su lugar, se importa el módulo que contiene el método de extensión, si es necesario que, para volver a ponerlo en el ámbito. Después del módulo que contiene `Print` está en ámbito, se puede llamar al método como si fuera un método de instancia ordinario que no toma ningún argumento, como `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]  
  
 El ejemplo siguiente, `PrintAndPunctuate`, también es una extensión <xref:System.String>, esta vez definida con dos parámetros. El primer parámetro, `aString`, Establece que el método de extensión extiende <xref:System.String>. El segundo parámetro, `punc`, está pensado para ser una cadena de signos de puntuación que se pasa como argumento cuando se llama al método. El método muestra la cadena seguida de los signos de puntuación.  
  
 [!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]  
  
 Se llama al método enviando un argumento de cadena para `punc`: `example.PrintAndPunctuate(".")`  
  
 El ejemplo siguiente muestra `Print` y `PrintAndPunctuate` definen y se invocan. <xref:System.Runtime.CompilerServices> se importa en el módulo de definición para permitir el acceso al atributo de extensión.  
  
### <a name="code"></a>Código  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 A continuación, los métodos de extensión se incluyen en el ámbito y se llama.  
  
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
  
### <a name="comments"></a>Comentarios  
 Todo lo que son necesaria que sea capaz de ejecutar estos comandos o métodos de extensión similares es que ser en el ámbito. Si el módulo que contiene un método de extensión está en ámbito, está visible en IntelliSense y pueden llamarse como si fuera un método de instancia normal.  
  
 Tenga en cuenta que cuando se invocan los métodos, se envía ningún argumento el primer parámetro. Parámetro `aString` en el método anterior definiciones se enlaza a `example`, la instancia de `String` que los llama. El compilador usará `example` como el argumento que se envía al primer parámetro.  
  
 Si se llama a un método de extensión para un objeto que se establece en `Nothing`, ejecuta el método de extensión. Esto no es aplicable a los métodos normales de la instancia. Puede comprobar explícitamente si `Nothing` en el método de extensión.  
  
## <a name="types-that-can-be-extended"></a>Tipos que se pueden extender  
 Puede definir un método de extensión en la mayoría de los tipos que se puede representar en una lista de parámetros de Visual Basic, incluidas las siguientes:  
  
- Clases (tipos de referencia)  
  
- Estructuras (tipos de valor)  
  
- Interfaces  
  
- Delegados  
  
- Argumentos ByRef y ByVal  
  
- Parámetros de método genérico  
  
- Matrices  
  
 Puesto que el primer parámetro especifica el tipo de datos que el método de extensión extiende, es necesario y no puede ser opcional. Por ese motivo, `Optional` parámetros y `ParamArray` parámetros no pueden ser el primer parámetro de la lista de parámetros.  
  
 No se consideran los métodos de extensión de enlace más tarde. En el ejemplo siguiente, la instrucción `anObject.PrintMe()` provoca un <xref:System.MissingMemberException> excepción, la misma excepción que vería si el segundo `PrintMe` definición de método de extensión se eliminaron.  
  
 [!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Métodos de extensión proporcionan una manera eficaz y conveniente para extender un tipo existente. Sin embargo, para poder utilizarlos correctamente, hay algunos puntos a tener en cuenta. Estas consideraciones se aplican principalmente a los autores de bibliotecas de clases, pero podrían afectar a cualquier aplicación que use métodos de extensión.  
  
 Más en general, los métodos de extensión que se agregan a los tipos que no es propietario son más vulnerables a los métodos de extensión que se agregan a los tipos que usted controla. Pueden ocurrir varias cosas en las clases que no es propietario que pueden interferir con sus métodos de extensión.  
  
- Si existe cualquier miembro de instancia accesible con una firma que es compatible con los argumentos de la instrucción de llamada con ningún argumento necesarias al parámetro las conversiones de restricción, se usará el método de instancia con preferencia a cualquier método de extensión. Por lo tanto, si se agrega un método de instancia adecuado para una clase en algún momento, un miembro existente de extensión que dependen de sea inaccesible.  
  
- El autor de un método de extensión no puede impedir que otros programadores escribir métodos de extensión conflictivos que pueden tener prioridad sobre la extensión original.  
  
- Puede mejorar la solidez colocando los métodos de extensión en su propio espacio de nombres. Los consumidores de la biblioteca, a continuación, pueden incluir un espacio de nombres o excluirlo o seleccionar entre los espacios de nombres, por separado del resto de la biblioteca.  
  
- Puede ser más seguro extender interfaces que es extender clases, especialmente si no posee la interfaz o clase. Un cambio en una interfaz afecta a todas las clases que lo implementa. Por lo tanto, el autor puede ser menos probable agregar o cambiar métodos en una interfaz. Sin embargo, si una clase implementa dos interfaces que tienen métodos de extensión con la misma firma, ninguno de los métodos extensión está visible.  
  
- Extender el tipo más específico que puede. En una jerarquía de tipos, si selecciona un tipo del que se derivan muchos otros tipos, hay niveles de posibilidades para la introducción de los métodos de instancia u otros métodos de extensión que podrían interferir con el suyo.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>Propiedades, métodos de instancia y métodos de extensión  
 Cuando un método de instancia en el ámbito tiene una firma que es compatible con los argumentos de una instrucción de llamada, se elige el método de instancia con preferencia a cualquier método de extensión. El método de instancia tiene prioridad incluso si el método de extensión es una coincidencia mejor. En el ejemplo siguiente, `ExampleClass` contiene un método de instancia denominado `ExampleMethod` que tiene un parámetro de tipo `Integer`. Método de extensión `ExampleMethod` extiende `ExampleClass`, y tiene un parámetro de tipo `Long`.  
  
 [!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]  
  
 La primera llamada a `ExampleMethod` en el código siguiente llama al método de extensión, porque `arg1` es `Long` y sólo es compatible con la `Long` parámetro del método de extensión. La segunda llamada a `ExampleMethod` tiene un `Integer` argumento, `arg2`, y llama al método de instancia.  
  
 [!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]  
  
 Ahora invierta los tipos de datos de los parámetros en los dos métodos:  
  
 [!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]  
  
 Esta vez el código en `Main` llama al método dos veces. Esto es porque ambos `arg1` y `arg2` tiene una conversión de ampliación a `Long`, y el método de instancia tiene prioridad sobre el método de extensión en ambos casos.  
  
 [!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]  
  
 Por lo tanto, un método de extensión no puede reemplazar un método de instancia existente. Sin embargo, cuando un método de extensión tiene el mismo nombre que un método de instancia pero las firmas no entran en conflicto, se pueden acceder ambos métodos. Por ejemplo, si clase `ExampleClass` contiene un método denominado `ExampleMethod` que toma ningún argumento, los métodos de extensión con el mismo nombre pero se permiten firmas diferentes, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]  
  
 La salida de este código es como sigue:  
  
 `Extension method`  
  
 `Instance method`  
  
 La situación es más fácil con propiedades: si un método de extensión tiene el mismo nombre que una propiedad de la clase que extiende, el método de extensión no está visible y no es accesible.  
  
## <a name="extension-method-precedence"></a>Prioridad del método de extensión  
 Cuando dos métodos de extensión que tienen firmas idénticas están en ámbito y accesible, se invocará el uno con prioridad más alta. Prioridad de un método de extensión se basa en el mecanismo utilizado para poner el método en el ámbito. En la lista siguiente se muestra la jerarquía de precedencia, de mayor a menor.  
  
1. Métodos de extensión definidos dentro del módulo actual.  
  
2. Métodos de extensión tipos definidos por el dentro de datos en el espacio de nombres actual o cualquiera de sus elementos primarios, con espacios de nombres secundarios tienen mayor prioridad que los espacios de nombres primario.  
  
3. Métodos de extensión definidos dentro de cualquier tipo de importaciones en el archivo actual.  
  
4. Métodos de extensión definidos dentro de cualquier importación de espacio de nombres en el archivo actual.  
  
5. Métodos de extensión definidos dentro de cualquier tipo de nivel de proyecto de importación.  
  
6. Métodos de extensión definidos dentro de cualquier importación de espacio de nombres de nivel de proyecto.  
  
 Si la prioridad no resuelve la ambigüedad, puede usar el nombre completo para especificar el método que está llamando. Si el `Print` método en el ejemplo anterior se define en un módulo denominado `StringExtensions`, el nombre completo es `StringExtensions.Print(example)` en lugar de `example.Print()`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Información general de atributos](../../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
