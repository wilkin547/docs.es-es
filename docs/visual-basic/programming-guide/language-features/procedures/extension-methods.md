---
title: Métodos de extensión (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 1cc2ccef09dd027c6f1e82f60ed4ac5f50db6ebe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="extension-methods-visual-basic"></a>Métodos de extensión (Visual Basic)
Métodos de extensión permiten a los programadores agregar funcionalidad personalizada a los tipos de datos que ya se han definido sin crear un nuevo tipo derivado. Métodos de extensión permiten escribir un método que se pueda llamar como si fuera un método de instancia del tipo existente.  
  
## <a name="remarks"></a>Comentarios  
 Un método de extensión puede ser solo un `Sub` procedimiento o una `Function` procedimiento. No se puede definir una propiedad de extensión, el campo o el evento. Todos los métodos de extensión se deben marcar con el atributo de extensión `<Extension()>` desde el <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres.  
  
 El primer parámetro en una definición de método de extensión especifica el tipo de datos que extiende el método. Cuando se ejecuta el método, el primer parámetro se enlaza a la instancia del tipo de datos que invoca el método.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se define un `Print` extensión a la <xref:System.String> tipo de datos. El método usa `Console.WriteLine` para mostrar una cadena. El parámetro de la `Print` método `aString`, Establece que el método extiende la <xref:System.String> clase.  
  
 [!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 Tenga en cuenta que la definición de método de extensión se marca con el atributo de extensión `<Extension()>`. Marcar el módulo en el que se define el método es opcional, pero se debe marcar cada método de extensión. <xref:System.Runtime.CompilerServices> se debe importar con el fin de obtener acceso al atributo de extensión.  
  
 Métodos de extensión se pueden declarar únicamente dentro de los módulos. Normalmente, el módulo en el que se define un método de extensión no es el mismo módulo que el uno en el que se llama. En su lugar, se importa el módulo que contiene el método de extensión, si es necesario que, para volver a ponerlo en el ámbito. Después del módulo que contiene `Print` está en el ámbito, se puede llamar al método como si fuera un método de instancia normal que no toma ningún argumento, como `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 El ejemplo siguiente, `PrintAndPunctuate`, también es una extensión <xref:System.String>, pero esta vez definida con dos parámetros. El primer parámetro, `aString`, Establece que el método de extensión extiende <xref:System.String>. El segundo parámetro, `punc`, está diseñada para ser una cadena de signos de puntuación que se pasa como argumento cuando se llama al método. El método muestra la cadena seguida de los signos de puntuación.  
  
 [!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 Se llama al método mediante el envío de un argumento de cadena para `punc`: `example.PrintAndPunctuate(".")`  
  
 El ejemplo siguiente muestra `Print` y `PrintAndPunctuate` define y llama. <xref:System.Runtime.CompilerServices> se importa en el módulo de definición para habilitar el acceso al atributo de extensión.  
  
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
 Todo lo que son necesaria que sea capaz de ejecutar estos o métodos de extensión similares es que estén en el ámbito. Si el módulo que contiene un método de extensión está en el ámbito, está visible en IntelliSense y puede llamarse como si fuera un método de instancia normal.  
  
 Tenga en cuenta que cuando se invocan los métodos, se envía ningún argumento para el primer parámetro. Parámetro `aString` en el método anterior definiciones se enlaza a `example`, la instancia de `String` que llama. El compilador usa `example` como el argumento enviado al primer parámetro.  
  
 Si se llama a un método de extensión para un objeto que se establece en `Nothing`, se ejecuta el método de extensión. Esto no se aplica a los métodos de instancia normal. Puede comprobar explícitamente si hay `Nothing` en el método de extensión.  
  
## <a name="types-that-can-be-extended"></a>Tipos que se pueden extender  
 Puede definir un método de extensión en la mayoría de los tipos que se puede representar en una lista de parámetros de Visual Basic, incluidas las siguientes:  
  
-   Clases (tipos de referencia)  
  
-   Estructuras (tipos de valor)  
  
-   Interfaces  
  
-   Delegados  
  
-   Argumentos ByRef y ByVal  
  
-   Parámetros de método genérico  
  
-   Matrices  
  
 Dado que el primer parámetro especifica el tipo de datos que extiende el método de extensión, es necesario y no puede ser opcional. Por esta razón, `Optional` parámetros y `ParamArray` parámetros no pueden ser el primer parámetro de la lista de parámetros.  
  
 Métodos de extensión no se consideran en el enlace más tarde. En el ejemplo siguiente, la instrucción `anObject.PrintMe()` genera un <xref:System.MissingMemberException> excepción, la misma excepción que vería si el segundo `PrintMe` definición de método de extensión se eliminaron.  
  
 [!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Métodos de extensión proporcionan una manera eficaz y conveniente para extender un tipo existente. Sin embargo, para poder utilizarlos correctamente, hay algunos puntos a tener en cuenta. Estas consideraciones se aplican principalmente a los autores de bibliotecas de clases, pero podrían afectar a cualquier aplicación que utilice los métodos de extensión.  
  
 Más generalmente, los métodos de extensión que se agregan a los tipos que no poseen son más vulnerables que agregó a tipos que controlan los métodos de extensión. Se pueden producir varios significados en clases no es propietario que pueden interferir con los métodos de extensión.  
  
-   Si existe cualquier miembro de instancia accesible que tenga una firma que es compatible con los argumentos en la instrucción que realiza la llamada, con no necesarias del argumento al parámetro de las conversiones de restricción, se utilizará el método de instancia con preferencia a cualquier método de extensión. Por lo tanto, si un método de instancia adecuado se agrega a una clase en algún momento, un miembro de extensión existente que se basan en puede quedar inaccesible.  
  
-   El autor de un método de extensión no puede impedir que otros programadores escribir métodos de extensión en conflicto que pueden tener prioridad sobre la extensión original.  
  
-   Puede mejorar la solidez colocando los métodos de extensión en su propio espacio de nombres. Los consumidores de la biblioteca, a continuación, pueden incluir un espacio de nombres o excluirla o seleccionar entre los espacios de nombres, independientemente del resto de la biblioteca.  
  
-   Puede ser más seguro extender interfaces de es extender clases, especialmente si no posee la interfaz o clase. Un cambio en una interfaz afecta a cada clase que lo implemente. Por lo tanto, el autor puede ser menos probable que agregar o cambiar los métodos en una interfaz. Sin embargo, si una clase implementa dos interfaces que tienen métodos de extensión con la misma firma, ninguno de los métodos extensión está visible.  
  
-   Ampliar el tipo más específico que puede. En una jerarquía de tipos, si selecciona un tipo desde el que se derivan muchos otros tipos, hay niveles de posibilidades para la inclusión de métodos de instancia u otros métodos de extensión que podrían interferir con el suyo.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>Propiedades, métodos de instancia y métodos de extensión  
 Cuando un método de instancia en el ámbito tiene una firma que es compatible con los argumentos de una instrucción de llamada, se elige el método de instancia con preferencia a cualquier método de extensión. El método de instancia tiene prioridad incluso si el método de extensión es una coincidencia mejor. En el ejemplo siguiente, `ExampleClass` contiene un método de instancia llamado `ExampleMethod` que tiene un parámetro de tipo `Integer`. Método de extensión `ExampleMethod` extiende `ExampleClass`, y tiene un parámetro de tipo `Long`.  
  
 [!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 La primera llamada a `ExampleMethod` en el código siguiente llama al método de extensión, porque `arg1` es `Long` y sólo es compatible con la `Long` parámetro del método de extensión. La segunda llamada a `ExampleMethod` tiene un `Integer` argumento, `arg2`, y llama al método de instancia.  
  
 [!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 Ahora invierta los tipos de datos de los parámetros en los dos métodos:  
  
 [!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 En el código en esta ocasión `Main` dos veces que se llama al método. Esto es porque ambos `arg1` y `arg2` tiene una conversión de ampliación a `Long`, y el método de instancia tiene prioridad sobre el método de extensión en ambos casos.  
  
 [!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 Por lo tanto, un método de extensión no puede reemplazar un método de instancia existente. Sin embargo, cuando un método de extensión tiene el mismo nombre que un método de instancia, pero las firmas no entran en conflicto, ambos métodos son accesibles. Por ejemplo, si clase `ExampleClass` contiene un método denominado `ExampleMethod` que toma ningún argumento, los métodos de extensión con el mismo nombre pero se permiten firmas diferentes, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 El resultado de este código es como sigue:  
  
 `Extension method`  
  
 `Instance method`  
  
 La situación es más fácil con propiedades: si un método de extensión tiene el mismo nombre que una propiedad de la clase que extiende, el método de extensión no está visible y no son accesibles.  
  
## <a name="extension-method-precedence"></a>Prioridad del método de extensión  
 Cuando dos métodos de extensión que tienen firmas idénticas están en el ámbito y son accesibles, se invocará el uno con prioridad más alta. Prioridad de un método de extensión se basa en el mecanismo utilizado para devolver el método en el ámbito. En la lista siguiente muestra la jerarquía de prioridad, de mayor a menor.  
  
1.  Métodos de extensión definidos dentro del módulo actual.  
  
2.  Métodos de extensión definen dentro de datos tipos en el espacio de nombres actual o cualquiera de sus elementos primarios, con espacios de nombres secundarios tener mayor prioridad que los espacios de nombres primario.  
  
3.  Métodos de extensión definidos dentro de cualquier tipo de importaciones del archivo actual.  
  
4.  Métodos de extensión definidos dentro de cualquier importación de espacio de nombres en el archivo actual.  
  
5.  Métodos de extensión definidos dentro de cualquier tipo de nivel de proyecto de importaciones.  
  
6.  Métodos de extensión definidos dentro de cualquier importación de espacio de nombres de nivel de proyecto.  
  
 Si la prioridad no resolver la ambigüedad, puede usar el nombre completo para especificar el método que está llamando. Si el `Print` método en el ejemplo anterior se define en un módulo denominado `StringExtensions`, el nombre completo es `StringExtensions.Print(example)` en lugar de `example.Print()`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Parámetros opcionales](./optional-parameters.md)  
 [Matrices de parámetros](./parameter-arrays.md)  
 [Información general de atributos](../../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
