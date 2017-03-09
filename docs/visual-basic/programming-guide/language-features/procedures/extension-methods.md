---
title: "M&#233;todos de extensi&#243;n (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ExtensionMethods"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "extender tipos de datos"
  - "métodos de extensión [Visual Basic]"
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 41
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 41
---
# M&#233;todos de extensi&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los métodos de extensión permiten a los desarrolladores agregar funcionalidad personalizada a los tipos de datos ya definidos sin crear un nuevo tipo derivado.  Los métodos de extensión permiten escribir un método al que se puede llamar como si fuera un método de instancia del tipo existente.  
  
## Comentarios  
 Un método de extensión puede ser únicamente un procedimiento `Sub` o un procedimiento `Function`.  No se puede definir ninguna propiedad, campo o evento de extensión.  Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, del espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=fullName>.  
  
 El primer parámetro de una definición de método de extensión especifica qué tipo de datos extiende el método.  Cuando se ejecuta el método, el primer parámetro se enlaza a la instancia del tipo de datos que invoca al método.  
  
## Ejemplo  
  
### Descripción  
 En el siguiente ejemplo se define una extensión `Print` para el tipo de datos <xref:System.String>.  El método usa `Console.WriteLine` para mostrar una cadena.  El parámetro del método `Print`, `aString`, establece que el método de extensión extiende la clase <xref:System.String>.  
  
 [!code-vb[VbVbalrExtensionMethods#1](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/StringExtensions.vb#1)]  
  
 Observe que la definición de método de extensión se marca con el atributo de extensión `<Extension()>`.  Marcar el módulo en el que se define el método es opcional, pero se debe marcar cada método de extensión.  <xref:System.Runtime.CompilerServices> debe importarse para poder obtener acceso al atributo de extensión.  
  
 Los métodos de extensión se pueden declarar únicamente dentro de los módulos.  Normalmente, el módulo en el que se define un método de extensión no es el mismo que el módulo en el que se llama.  En su lugar, se importa el módulo que contiene el método de extensión, si fuera necesario, para incluirlo en el ámbito.  Después de que el módulo que contiene `Print` esté en el ámbito, se puede llamar al método como si fuera un método de instancia ordinario que no toma argumentos, como `ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods#2](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Class1.vb#2)]  
  
 En el ejemplo siguiente, `PrintAndPunctuate`, también es una extensión de <xref:System.String>, esta vez definida con dos parámetros.  El primer parámetro, `aString`, establece que el método de extensión extiende <xref:System.String>.  El segundo parámetro, `punc`, está pensado para ser una cadena de signos de puntuación que se pasa como argumento cuando se llama al método.  El método muestra la cadena seguida de los signos de puntuación.  
  
 [!code-vb[VbVbalrExtensionMethods#3](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Class2.vb#3)]  
  
 Se llama al método enviando un argumento de cadena para `punc`: `example.PrintAndPunctuate(".")`  
  
 En el siguiente ejemplo, se muestra cómo se definen y se invocan `Print` y `PrintAndPunctuate`.  <xref:System.Runtime.CompilerServices> se importa en el módulo de definición para permitir el acceso al atributo de extensión.  
  
### Código  
  
```vb#  
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
  
 Después, los métodos de extensión se incluyen en el ámbito y se llaman.  
  
```vb#  
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
  
### Comentarios  
 Todo esto es necesario para poder ejecutar estos métodos o métodos de extensión similares que están en el ámbito.  Si el módulo que contiene un método de extensión está en el ámbito, está visible en IntelliSense y se le llama como si fuera un método de instancia normal.  
  
 Observe que cuando se invocan los métodos, no se envía ningún argumento para el primer parámetro.  El parámetro, `aString` en las definiciones de método anteriores, se enlaza a `example`, la instancia de `String` que los llama.  El compilador usará `example` como el argumento que se envía al primer parámetro.  
  
 Si un método de extensión se llama para un objeto que está establecido en `Nothing`, el método de extensión se ejecuta.  Esto no se aplica a los métodos normales de la instancia.  Puede comprobar explícitamente si hay `Nothing` en el método de extensión.  
  
## Tipos que se pueden extender  
 Puede definir un método de extensión en la mayoría de los tipos que se pueden representar en una lista de parámetros de Visual Basic, incluidos los siguientes:  
  
-   Clases \(tipos de referencia\)  
  
-   Estructuras \(tipos de valor\)  
  
-   Interfaces  
  
-   Delegados  
  
-   Argumentos ByRef y ByVal  
  
-   Parámetros de método genérico  
  
-   Matrices  
  
 Puesto que el primer parámetro especifica el tipo de datos que el método de extensión extiende, es obligatorio y no puede ser opcional.  Por esa razón, los parámetros `Optional` y `ParamArray` no pueden ser el primer parámetro de la lista de parámetros.  
  
 Los métodos de extensión no se consideran en los enlaces en tiempo de ejecución.  En el siguiente ejemplo, la instrucción `anObject.PrintMe()` genera una excepción <xref:System.MissingMemberException>, la misma excepción que se produciría si se eliminara la segunda definición del método de extensión `PrintMe`.  
  
 [!code-vb[VbVbalrExtensionMethods#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Class6.vb#9)]  
  
## Procedimientos recomendados  
 Los métodos de extensión proporcionan una manera conveniente y eficaz de extender un tipo existente.  Sin embargo, para usarlos correctamente se deben tener en cuenta algunos puntos.  Estas consideraciones se aplican principalmente a los autores de bibliotecas de clases, pero podrían afectar a cualquier aplicación que use métodos de extensión.  
  
 Más en general, los métodos de extensión que agrega a los tipos de los que no es propietario son más vulnerables que los métodos de extensión agregados a los tipos que controla.  Se pueden producir algunos conflictos en las clases de las que no es propietario que pueden interferir con sus métodos de extensión.  
  
-   Si existe cualquier miembro de instancia accesible con una firma compatible con los argumentos en la instrucción de llamada, sin requerir conversiones de restricción del argumento al parámetro, el método de instancia se usará antes que cualquier método de extensión.  Por consiguiente, si se agrega un método de instancia adecuado a una clase en un momento dado, puede que un miembro de extensión existente en el que confía se vuelva inaccesible.  
  
-   El autor de un método de extensión no puede evitar que otros programadores escriban métodos de extensión conflictivos que pueden tener prioridad sobre la extensión original.  
  
-   Puede mejorar la solidez colocando los métodos de extensión en su propio espacio de nombres.  Entonces, los usuarios de su biblioteca pueden incluir un espacio de nombres o excluirlo, o bien seleccionar entre los espacios de nombres, por separado en el resto de la biblioteca.  
  
-   Puede ser más seguro extender interfaces que extender clases, sobre todo si no posee la interfaz o la clase.  Un cambio en una interfaz afecta a cada clase que la implementa.  Por consiguiente, es menos probable que el autor pueda agregar o cambiar métodos en una interfaz.  Sin embargo, si una clase implementa dos interfaces que tienen métodos de extensión con la misma firma, ninguno de los métodos de extensión está visible.  
  
-   Extienda el tipo más específico que pueda.  En una jerarquía de tipos, si selecciona un tipo del que se derivan muchos otros tipos, hay niveles de posibilidades para la inclusión de métodos de instancia u otros métodos de extensión que podrían interferir con el suyo.  
  
## Métodos de extensión, métodos de instancia y propiedades  
 Cuando un método de instancia dentro del ámbito tiene una firma que es compatible con los argumentos de una instrucción de llamada, se elige el método de instancia de preferencia a cualquier método de extensión.  El método de instancia tiene la prioridad aun cuando el método de extensión tenga una mejor coincidencia.  En el ejemplo siguiente, `ExampleClass` contiene un método de instancia denominado `ExampleMethod` que tiene un parámetro de tipo `Integer`.  El método de extensión `ExampleMethod` extiende `ExampleClass` y tiene un parámetro de tipo `Long`.  
  
 [!code-vb[VbVbalrExtensionMethods#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Class4.vb#4)]  
  
 La primera llamada a `ExampleMethod` en el código siguiente llama al método de extensión, porque `arg1` es `Long` y sólo es compatible con el parámetro `Long` en el método de extensión.  La segunda llamada a `ExampleMethod` tiene un argumento `Integer`, `arg2`, y llama al método de instancia.  
  
 [!code-vb[VbVbalrExtensionMethods#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Class4.vb#5)]  
  
 Ahora invierta los tipos de datos de los parámetros en los dos métodos:  
  
 [!code-vb[VbVbalrExtensionMethods#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Class5.vb#6)]  
  
 Ahora el código de `Main` llama al método de instancia las dos veces.  Esto se debe a que `arg1` y `arg2` tienen una conversión de ampliación a `Long`, y el método de instancia tiene prioridad sobre el método de extensión en ambos casos.  
  
 [!code-vb[VbVbalrExtensionMethods#7](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Class5.vb#7)]  
  
 Por lo tanto, un método de extensión no puede reemplazar a un método de instancia existente.  Sin embargo, cuando un método de extensión tiene el mismo nombre que un método de instancia pero las firmas no entran en conflicto, se puede tener acceso a ambos métodos.  Por ejemplo, si la clase `ExampleClass` contiene un método denominado `ExampleMethod` que no toma ningún argumento, se permiten métodos de extensión con el mismo nombre pero con firmas diferentes, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrExtensionMethods#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/ConsoleApplication1/Module3.vb#8)]  
  
 Los resultados de este código son los siguientes:  
  
 `Extension method`  
  
 `Instance method`  
  
 La situación es más fácil con propiedades: si un método de extensión tiene el mismo nombre que una propiedad de la clase que extiende, el método de extensión no está visible y no se puede tener acceso a él.  
  
## Prioridad del método de extensión  
 Cuando dos métodos de extensión con firmas idénticas están en el ámbito y se encuentran accesibles, se invoca al de mayor prioridad.  La prioridad de un método de extensión se basa en el mecanismo que se usa para incluir al método en el ámbito.  La lista siguiente muestra la jerarquía de prioridad, de mayor a menor.  
  
1.  Métodos de extensión definidos dentro del módulo actual.  
  
2.  Métodos de extensión definidos dentro de los tipos de datos en el espacio de nombres actual o cualquiera de sus elementos primarios. Los espacios de nombres secundarios tienen mayor prioridad que los espacios de nombres primarios.  
  
3.  Métodos de extensión definidos dentro de cualquier tipo de importaciones en el archivo actual.  
  
4.  Métodos de extensión definidos dentro de cualquier importación de espacio de nombres en el archivo actual.  
  
5.  Métodos de extensión definidos dentro de cualquier tipo de importaciones de nivel de proyecto.  
  
6.  Métodos de extensión definidos dentro de cualquier importación de espacio de nombres de nivel de proyecto.  
  
 Si la prioridad no resuelve la ambigüedad, puede usar el nombre completo para especificar el método al que está llamando.  Si el método `Print` del ejemplo anterior se define en un módulo denominado `StringExtensions`, el nombre completo es `StringExtensions.Print(example)` en vez de `example.Print()`.  
  
## Vea también  
 <xref:System.Runtime.CompilerServices>   
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [Module \(Instrucción\)](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Matrices de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)