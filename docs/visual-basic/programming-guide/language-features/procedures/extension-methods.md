---
title: "Métodos de extensión (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ExtensionMethods
dev_langs:
- VB
helpviewer_keywords:
- extending data types
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 381fa0db2d92590d23ebd71a7823a8465e94a6e6
ms.lasthandoff: 03/13/2017

---
# <a name="extension-methods-visual-basic"></a>Métodos de extensión (Visual Basic)
Métodos de extensión permiten a los programadores agregar funcionalidad personalizada a los tipos de datos que ya están definidos sin crear un nuevo tipo derivado. Métodos de extensión permiten escribir un método que se puede llamar como si fuera un método de instancia del tipo existente.  
  
## <a name="remarks"></a>Comentarios  
 Un método de extensión puede ser sólo una `Sub` procedimiento o una `Function` procedimiento. No se puede definir una propiedad de extensión, campo o evento. Todos los métodos de extensión se deben marcar con el atributo de extensión `<Extension()>` desde el <xref:System.Runtime.CompilerServices?displayProperty=fullName>espacio de nombres.</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 El primer parámetro de una definición de método de extensión especifica qué tipo de datos extiende el método. Cuando se ejecuta el método, el primer parámetro se enlaza a la instancia del tipo de datos que invoca el método.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se define un `Print` extensión a la <xref:System.String>el tipo de datos.</xref:System.String> El método usa `Console.WriteLine` para mostrar una cadena. El parámetro de la `Print` método `aString`, Establece que el método extiende la <xref:System.String>clase.</xref:System.String>  
  
 [!code-vb[1 VbVbalrExtensionMethods](./codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 Observe que la definición del método de extensión está marcada con el atributo de extensión `<Extension()>`. Marcar el módulo en el que se define el método es opcional, pero se debe marcar cada método de extensión. <xref:System.Runtime.CompilerServices>se debe importar con el fin de obtener acceso al atributo de extensión.</xref:System.Runtime.CompilerServices>  
  
 Métodos de extensión se pueden declarar únicamente dentro de los módulos. Normalmente, el módulo en el que se define un método de extensión no es el mismo módulo que la que se llama. En su lugar, se importa el módulo que contiene el método de extensión, si debe ser para poner al alcance. Después del módulo que contiene `Print` está en el ámbito, el método puede llamarse como si fuera un método de instancia normal que no toma ningún argumento, como `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods&#2;](./codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 El ejemplo siguiente, `PrintAndPunctuate`, también es una extensión <xref:System.String>, esta vez definida con dos parámetros.</xref:System.String> El primer parámetro, `aString`, Establece que el método de extensión extiende <xref:System.String>.</xref:System.String> El segundo parámetro, `punc`, está pensado para ser una cadena de signos de puntuación que se pasa como argumento cuando se llama al método. El método muestra la cadena seguida de los signos de puntuación.  
  
 [!code-vb[VbVbalrExtensionMethods&3;](./codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 Se llama al método enviando un argumento de cadena para `punc`:`example.PrintAndPunctuate(".")`  
  
 El ejemplo siguiente muestra `Print` y `PrintAndPunctuate` define y llama. <xref:System.Runtime.CompilerServices>se importa en el módulo de definición para permitir el acceso al atributo de extensión.</xref:System.Runtime.CompilerServices>  
  
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
 Todo lo que es necesario para poder ejecutar estas o métodos de extensión similares es que estén en el ámbito. Si el módulo que contiene un método de extensión está en ámbito, está visible en IntelliSense y pueden llamarse como si fuera un método de instancia normal.  
  
 Observe que cuando se invocan los métodos, se envía ningún argumento para el primer parámetro. Parámetro `aString` en el método anterior, las definiciones se enlaza a `example`, la instancia de `String` que llama. El compilador usa `example` como el argumento enviado al primer parámetro.  
  
 Si se llama a un método de extensión para un objeto que se establece en `Nothing`, se ejecuta el método de extensión. No se aplica a los métodos de instancia normales. Puede comprobar explícitamente si `Nothing` en el método de extensión.  
  
## <a name="types-that-can-be-extended"></a>Tipos que se pueden extender  
 Puede definir un método de extensión en la mayoría de los tipos que se puede representar en una lista de parámetros de Visual Basic, incluidas las siguientes:  
  
-   Clases (tipos de referencia)  
  
-   Estructuras (tipos de valor)  
  
-   Interfaces  
  
-   Delegados  
  
-   Argumentos ByRef y ByVal  
  
-   Parámetros de método genérico  
  
-   Matrices  
  
 Dado que el primer parámetro especifica el tipo de datos que el método de extensión extiende, es necesario y no puede ser opcional. Por ese motivo, `Optional` parámetros y `ParamArray` parámetros no pueden ser el primer parámetro de la lista de parámetros.  
  
 Métodos de extensión no se consideran en el enlace más tarde. En el ejemplo siguiente, la instrucción `anObject.PrintMe()` provoca un <xref:System.MissingMemberException>de excepciones, la misma excepción que vería si el segundo `PrintMe` definición de método de extensión se eliminaron.</xref:System.MissingMemberException>  
  
 [!code-vb[VbVbalrExtensionMethods&#9;](./codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Métodos de extensión proporcionan una manera conveniente y eficaz de extender un tipo existente. Sin embargo, para usarlas correctamente, hay algunos puntos a tener en cuenta. Estas consideraciones se aplican principalmente a los autores de bibliotecas de clases, pero podrían afectar a cualquier aplicación que use métodos de extensión.  
  
 Más en general, los métodos de extensión que agrega a los tipos que no es propietario son más vulnerables que agrega a los tipos que controlan los métodos de extensión. Pueden ocurrir varias cosas en clases que no es propietario que pueden interferir con sus métodos de extensión.  
  
-   Si existe cualquier miembro de instancia accesible con una firma que es compatible con los argumentos de la instrucción de llamada con ningún conversiones de restricción necesarias del argumento al parámetro, se utilizará el método de instancia con preferencia a cualquier método de extensión. Por lo tanto, si un método de instancia adecuado se agrega a una clase en algún momento, un miembro de extensión existente que se basan en puede quedar inaccesible.  
  
-   El autor de un método de extensión no puede impedir que otros programadores escribir métodos de extensión en conflicto que pueden tener prioridad sobre la extensión original.  
  
-   Puede mejorar la solidez colocando los métodos de extensión en su propio espacio de nombres. Los consumidores de la biblioteca pueden incluir un espacio de nombres o excluirla o seleccionar uno de los espacios de nombres, por separado del resto de la biblioteca.  
  
-   Puede ser más seguro extender interfaces que es extender clases, sobre todo si no posee la interfaz o clase. Un cambio en una interfaz afecta a cada clase que lo implementa. Por lo tanto, el autor puede ser menos probable agregar o cambiar los métodos de una interfaz. Sin embargo, si una clase implementa dos interfaces que tienen métodos de extensión con la misma firma, ningún método de extensión está visible.  
  
-   Extender el tipo más específico que es posible. En una jerarquía de tipos, si selecciona un tipo del que se derivan muchos otros tipos, hay niveles de posibilidades para la introducción de métodos de instancia u otros métodos de extensión que podrían interferir con el suyo.  
  
## <a name="extension-methods-instance-methods-and-properties"></a>Métodos de extensión, métodos de instancia y propiedades  
 Cuando un método de instancia en el ámbito tiene una firma que es compatible con los argumentos de una instrucción de llamada, se elige el método de instancia con preferencia a cualquier método de extensión. El método de instancia tiene prioridad incluso si el método de extensión es una coincidencia mejor. En el ejemplo siguiente, `ExampleClass` contiene un método de instancia denominado `ExampleMethod` que tiene un parámetro de tipo `Integer`. Método de extensión `ExampleMethod` extiende `ExampleClass`, y tiene un parámetro de tipo `Long`.  
  
 [!code-vb[VbVbalrExtensionMethods Nº&4;](./codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 La primera llamada a `ExampleMethod` en el código siguiente llama al método de extensión, porque `arg1` es `Long` y sólo es compatible con la `Long` parámetro en el método de extensión. La segunda llamada a `ExampleMethod` tiene un `Integer` argumento, `arg2`, y llama al método de instancia.  
  
 [!code-vb[VbVbalrExtensionMethods&#5;](./codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 Ahora invierta los tipos de datos de los parámetros de los dos métodos:  
  
 [!code-vb[VbVbalrExtensionMethods Nº&6;](./codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 Esta vez el código en `Main` llama al método dos veces. Esto es porque ambos `arg1` y `arg2` tiene una conversión de ampliación a `Long`, y el método de instancia tiene prioridad sobre el método de extensión en ambos casos.  
  
 [!code-vb[VbVbalrExtensionMethods&#7;](./codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 Por lo tanto, un método de extensión no puede reemplazar un método de instancia existente. Sin embargo, cuando un método de extensión tiene el mismo nombre que un método de instancia pero las firmas no entran en conflicto, pueden tener acceso ambos métodos. Por ejemplo, si clase `ExampleClass` contiene un método denominado `ExampleMethod` que toma ningún argumento, los métodos de extensión con el mismo nombre pero firmas diferentes están permitidas, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrExtensionMethods Nº&8;](./codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 El resultado de este código es como sigue:  
  
 `Extension method`  
  
 `Instance method`  
  
 La situación es más fácil con propiedades: si un método de extensión tiene el mismo nombre que una propiedad de la clase que extiende, el método de extensión no está visible y no se tiene acceso.  
  
## <a name="extension-method-precedence"></a>Prioridad del método de extensión  
 Cuando dos métodos de extensión que tienen firmas idénticas están en el ámbito y son accesibles, se invocará el uno con prioridad más alta. Prioridad de un método de extensión se basa en el mecanismo utilizado para poner el método en el ámbito. La lista siguiente muestra la jerarquía de prioridad, de mayor a menor.  
  
1.  Métodos de extensión definidos dentro del módulo actual.  
  
2.  Métodos de extensión dentro de datos de tipos definen en el espacio de nombres actual o cualquiera de sus elementos primarios, con espacios de nombres secundarios tener mayor prioridad que los espacios de nombres primario.  
  
3.  Métodos de extensión definidos dentro de cualquier tipo de importaciones en el archivo actual.  
  
4.  Métodos de extensión definidos dentro de cualquier importación de espacio de nombres en el archivo actual.  
  
5.  Métodos de extensión definidos dentro de cualquier tipo de nivel de proyecto de importación.  
  
6.  Métodos de extensión definidos dentro de cualquier importación de espacio de nombres de nivel de proyecto.  
  
 Si la prioridad no resuelve la ambigüedad, puede utilizar el nombre completo para especificar el método al que se llama. Si el `Print` método en el ejemplo anterior se define en un módulo denominado `StringExtensions`, el nombre completo es `StringExtensions.Print(example)` en lugar de `example.Print()`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices></xref:System.Runtime.CompilerServices>   
 <xref:System.Runtime.CompilerServices.ExtensionAttribute></xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Parámetros opcionales](./optional-parameters.md)   
 [Matrices de parámetros](./parameter-arrays.md)   
 [Información general de atributos](../../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
