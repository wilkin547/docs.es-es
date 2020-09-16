---
title: Escribir aplicaciones grandes de .NET Framework que respondan
description: Escriba aplicaciones .NET grandes, con capacidad de respuesta o aplicaciones que procesan una gran cantidad de datos, como archivos o bases de datos.
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d74c7b8d80f02283cd681ed0118257ed926bdc83
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555255"
---
# <a name="writing-large-responsive-net-framework-apps"></a>Escribir aplicaciones grandes de .NET Framework que respondan

En este artículo se ofrecen varias sugerencias para mejorar el rendimiento de las aplicaciones .NET Framework de gran tamaño o de aquellas aplicaciones que procesan una gran cantidad de datos, como archivos o bases de datos. Estas sugerencias proceden de reescribir los compiladores de C# y Visual Basic en código administrado; además, el artículo incluye varios ejemplos reales del compilador de C#.
  
.NET Framework es muy productivo en la compilación de aplicaciones. Gracias a unos lenguajes potentes y seguros, así como a una amplia colección de bibliotecas, la compilación de aplicaciones resulta muy fructífera. Sin embargo, una gran productividad conlleva responsabilidad. Use todas las posibilidades de .NET Framework, pero prepárese para ajustar el rendimiento del código cuando sea necesario.
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a>Por qué el rendimiento del nuevo compilador afecta a su aplicación  
 El equipo .NET Compiler Platform («Roslyn») ha reescrito los compiladores de C# y Visual Basic en código administrado con el objetivo de proporcionar nuevas API para el modelado y análisis de código, la compilación de herramientas y la habilitación de experiencias, y también para permitir una experiencia mucho más enriquecedora en cuanto a código en Visual Studio. La reescritura de los compiladores y la compilación de experiencias de Visual Studio en los nuevos compiladores ha revelado información útil sobre el rendimiento que se puede emplear en cualquier aplicación de .NET Framework de gran tamaño o en cualquier aplicación que procese una gran cantidad de datos. No es necesario tener conocimientos sobre compiladores para beneficiarse de la información y los ejemplos del compilador de C#.
  
 Visual Studio usa las API de compilador para crear todas aquellas características de IntelliSense que adoran los usuarios: coloración de identificadores y palabras clave, listas de finalización de sintaxis, líneas en zigzag de errores, sugerencias sobre parámetros, emisión de código y acciones de código. Visual Studio proporciona esta ayuda mientras los desarrolladores escriben y modifican su código; Visual Studio debe responder en todo momento mientras el compilador modela continuamente el código que editan los desarrolladores.
  
 Cuando los usuarios finales interactúan con la aplicación, esperan una capacidad de respuesta adecuada. La escritura o la gestión de comandos nunca debe bloquearse. La ayuda debe aparecer rápidamente o desaparecer si el usuario continúa escribiendo. La aplicación debe evitar bloquear el subproceso de la interfaz de usuario con largos cálculos que ralenticen la aplicación.
  
 Para obtener más información sobre los compiladores de Roslyn, vea [el SDK de .net Compiler Platform](../../csharp/roslyn-sdk/index.md).
  
## <a name="just-the-facts"></a>Solo los hechos  
 Tenga en cuenta lo siguiente cuando ajuste el rendimiento y cree aplicaciones de .NET Framework con capacidad de respuesta.
  
### <a name="fact-1-dont-prematurely-optimize"></a>Hecho 1: No optimice prematuramente  
 Escribir código más complejo de lo necesario conlleva costes de mantenimiento, depuración y pulido. Los programadores experimentados saben intuitivamente cómo resolver problemas de código y cómo escribir un código más eficaz. Sin embargo, a veces optimizan el código de forma prematura. Por ejemplo, usan una tabla hash cuando con una simple matriz bastaría, o utilizan un almacenamiento en caché complicado que puede consumir memoria en vez de simplemente recalcular los valores. Incluso los programadores experimentados deben probar el rendimiento y analizar el código cuando se detectan problemas.
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a>Hecho 2: Si no realiza mediciones, solo tiene conjeturas  
 Los perfiles y las medidas no mienten. Los perfiles muestran si la CPU está totalmente cargada o si hay un bloqueo en E/S de disco. Los perfiles indican el tipo y la cantidad de memoria que se está asignando y si la CPU emplea mucho tiempo en la [recolección de elementos no utilizados](../../standard/garbage-collection/index.md).
  
 Establezca objetivos de rendimiento para los escenarios o las experiencias de cliente claves de la aplicación y escriba pruebas para medir el rendimiento.  Investigue los errores de las pruebas mediante el método científico: use perfiles como guía, cree hipótesis sobre el origen del problema y pruebe esas hipótesis con un experimento o cambio de código. Establezca una línea base de medidas de rendimiento a lo largo del tiempo con pruebas periódicas para así aislar los cambios que causan regresiones en el rendimiento. Si enfoca de manera rigurosa el trabajo de rendimiento, evitará perder el tiempo con actualizaciones de código que no necesita.
  
### <a name="fact-3-good-tools-make-all-the-difference"></a>Hecho 3: Las herramientas de calidad marcan la diferencia  
 Unas herramientas de calidad permiten profundizar rápidamente en los problemas de rendimiento más importantes (CPU, memoria o disco) y sirven para localizar el código que provoca esos cuellos de botella. Microsoft incluye una variedad de herramientas de rendimiento como [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) y [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).
  
 PerfView es una herramienta gratuita muy potente que sirve para centrarse en los problemas con raíces profundas como, por ejemplo, E/S de disco, eventos de GC y memoria. Puede capturar eventos de [Seguimiento de eventos para Windows](../wcf/samples/etw-tracing.md) (ETW) relacionados con el rendimiento y ver fácilmente información por aplicación, por proceso, por pila y por subproceso. PerfView muestra la cantidad y el tipo de memoria que asigna la aplicación, así como las funciones o pilas de llamadas que contribuyen en determinada medida a las asignaciones de memoria. Para más información, vea los completos artículos de ayuda, las demostraciones y los vídeos que se incluyen con la herramienta (como los [tutoriales de PerfView](https://channel9.msdn.com/Series/PerfView-Tutorial) de Channel 9).
  
### <a name="fact-4-its-all-about-allocations"></a>Hecho 4: La clave está en las asignaciones  
 Podría pensarse que la compilación de una aplicación de .NET Framework que muestre una buena capacidad de respuesta depende de la utilización de los algoritmos —como usar una ordenación rápida en vez de una de burbuja—, pero no es así. El factor de mayor peso a la hora de compilar una aplicación diligente es la asignación de memoria, sobre todo cuando la aplicación es muy grande o procesa grandes cantidades de datos.
  
 Casi todo el trabajo de compilar las experiencias de IDE con las nuevas API de compilador se invirtió en evitar las asignaciones y administrar las estrategias de almacenamiento en caché. El seguimiento de PerfView muestra que el rendimiento de los nuevos compiladores de C# y Visual Basic rara vez está asociado a la CPU. Los compiladores pueden estar asociados a E/S al leer miles o millones de líneas de código, al leer metadatos o al emitir código generado. Los retrasos del subproceso de la interfaz de usuario se deben prácticamente todos a la recolección de elementos no utilizados. La GC de .NET Framework está ajustada para optimizar el rendimiento y una gran parte de su trabajo se realiza mientras se ejecuta el código de la aplicación. Pero una única asignación puede desencadenar una costosa recolección [gen2](../../standard/garbage-collection/fundamentals.md) y detener todos los subprocesos.
  
## <a name="common-allocations-and-examples"></a>Asignaciones comunes y ejemplos  
 Las expresiones de ejemplo que se incluyen en esta sección tiene asignaciones que parecen pequeñas. Aun así, si una aplicación grande ejecuta las expresiones un número de veces suficiente, pueden producirse cientos de megabytes, e incluso gigabytes, de asignaciones. Por ejemplo, durante las pruebas de un minuto en las que se simulaba la escritura de un desarrollador en el editor se asignaron gigabytes de memoria, y esto hizo que el equipo de rendimiento se centrase en los escenarios de escritura.
  
### <a name="boxing"></a>Boxing  
 La [conversión boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) se produce cuando se ajustan en un objeto tipos de valores que normalmente residen en la pila o en estructuras de datos. Es decir, se asigna un objeto para contener los datos y luego se devuelve un puntero al objeto. .NET Framework a veces realiza una conversión boxing de valores debido a la signatura de un método o al tipo de la ubicación de almacenamiento. El encapsulamiento de un tipo de valor en un objeto obliga a asignar memoria. Muchas operaciones de conversión boxing puede sumar megabytes o gigabytes de asignaciones a la aplicación, lo que significa que esta provocará más GC. .NET Framework y los compiladores de lenguaje evitan la conversión boxing siempre que pueden, pero a veces se produce en el momento menos esperado.
  
 Para ver la conversión boxing en PerfView, inicie un seguimiento y mire GC Heap Alloc Stacks bajo el nombre de proceso de su aplicación (recuerde, PerfView informa de todos los procesos). Si ve tipos como <xref:System.Int32?displayProperty=nameWithType> y <xref:System.Char?displayProperty=nameWithType> en las asignaciones, significa que está realizando una conversión boxing de tipos de valores. Si se elige uno de estos tipos, se mostrarán las pilas y las funciones en las que se han convertido.
  
 **Ejemplo 1: métodos de cadena y argumentos de tipo de valor**  
  
 En este código de ejemplo se muestra una potencial conversión boxing innecesaria y excesiva:  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 El código proporciona funcionalidad de registro, por lo que la aplicación puede llamar a la función `Log` frecuentemente, quizá millones de veces. El problema es que la llamada a `string.Format` se resuelve a la sobrecarga <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29>.
  
 Esta sobrecarga necesita que .NET Framework realice una conversión boxing de los valores `int` para transformarlos en objetos y pasarlos a esta llamada al método. Una solución parcial es llamar a `id.ToString()` y `size.ToString()`, y pasar todas las cadenas (que son objetos) a la llamada `string.Format`. La llamada a `ToString()` no asigna una cadena, pero esa asignación se producirá de todos modos en `string.Format`.
  
 Puede considerar que esta llamada básica a `string.Format` es simplemente concatenación de cadenas, por lo que puede escribir este código en su lugar:  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 No obstante, esa línea de código introduce una asignación boxing porque se compila en <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>. .NET Framework debe realizar una conversión boxing del literal de carácter para invocar a `Concat`.  
  
 **Corrección para el ejemplo 1**  
  
 La solución es sencilla. Simplemente reemplace el literal de carácter por un literal de cadena; este no provoca conversión boxing porque las cadenas ya son objetos:  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 **Ejemplo 2: conversión boxing de enum**  
  
 Este ejemplo fue el causante de una cantidad enorme de asignación en los nuevos compiladores de C# y Visual Basic debido al uso frecuente de tipos de enumeración, especialmente en operaciones de búsqueda en diccionarios.
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 Este problema es muy sutil. PerfView consideraba esto como una conversión boxing de <xref:System.Enum.GetHashCode>, ya que, por motivos de implementación, el método realiza una conversión boxing de la representación subyacente del tipo de enumeración. Si observa detenidamente en PerfView, puede ver dos asignaciones de conversión boxing para cada llamada a <xref:System.Enum.GetHashCode>. El compilador inserta una y .NET Framework inserta la otra.
  
 **Corrección para el ejemplo 2**  
  
 Es muy fácil evitar ambas asignaciones si se convierte a la representación subyacente antes de llamar a <xref:System.Enum.GetHashCode>:  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 Otra fuente común de conversión boxing en tipos de enumeración es el método <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType>. Es necesario realizar una conversión boxing del argumento pasado a <xref:System.Enum.HasFlag%28System.Enum%29>. En la mayoría de los casos, el reemplazo de llamadas a <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> con una prueba bit a bit es más sencilla y sin asignaciones.
  
 No olvide el primer hecho de rendimiento (no optimice prematuramente) y no empiece a reescribir todo su código de este modo. Tenga en cuenta los costes de la conversión boxing, pero, antes de cambiar el código, perfile su aplicación y busque los puntos conflictivos.
  
### <a name="strings"></a>Cadenas  
 La manipulación de cadenas es uno de los mayores causantes de las asignaciones y con frecuencia aparece entre el top cinco de las asignaciones en PerfView. Los programas usan cadenas para serialización, JSON y API REST. Las cadenas se pueden usar como constantes de programación para interoperar con sistemas cuando no se pueden usar tipos de enumeración. Cuando la generación de perfiles muestra que las cadenas están afectando enormemente al rendimiento, busque llamadas a métodos <xref:System.String> como <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, etc. El uso de <xref:System.Text.StringBuilder> para evitar el crear una cadena a partir de muchos fragmentos sirve de ayuda, pero incluso asignando el objeto <xref:System.Text.StringBuilder> puede originar un cuello de botella que es necesario administrar.
  
 **Ejemplo 3: operaciones de cadena**  
  
 El compilador de C# tenía este código que escribe el texto de un comentario de documento XML con formato:  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 Como se puede ver, en este código hay mucha manipulación de cadenas. El código usa métodos de biblioteca para dividir líneas en cadenas independientes, para reducir espacio en blanco, para comprobar si el argumento `text` es un comentario de documentación XML y para extraer subcadenas de las líneas.
  
 En la primera línea dentro de `WriteFormattedDocComment`, la llamada `text.Split` asigna una nueva matriz de tres elementos como argumento cada vez que se llama. El compilador tiene que emitir código para asignar esta matriz en cada ocasión. Eso se debe a que el compilador no sabe si <xref:System.String.Split%2A> almacena la matriz en algún lugar donde pueda ser modificada por otro código, lo que afectaría a las llamadas posteriores a `WriteFormattedDocComment`. La llamada a <xref:System.String.Split%2A> también asigna una cadena para cada línea en `text` y asigna otra memoria para realizar la operación.
  
 `WriteFormattedDocComment` tiene tres llamadas al método <xref:System.String.TrimStart%2A>. Dos están en bucles internos que duplican el trabajo y las asignaciones. Para empeorar las cosas, la llamada al método <xref:System.String.TrimStart%2A> sin argumentos asigna una matriz vacía (para el parámetro `params`) además del resultado de la cadena.
  
 Por último, hay una llamada al método <xref:System.String.Substring%2A>, que normalmente asigna una cadena nueva.
  
 **Corrección para el ejemplo 3**  
  
 A diferencia de los ejemplos anteriores, estas asignaciones no se resuelven con pequeñas asignaciones. Es necesario dar un paso atrás, observar el problema y enfocarlo de manera diferente. Por ejemplo, observará que el argumento para `WriteFormattedDocComment()` es una cadena que tiene toda la información que necesita el método, por lo que el código podría hacer más labores de indización en vez de asignar muchas cadenas parciales.
  
 El equipo de rendimiento del compilador abordó estas asignaciones con un código como el siguiente:  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc...
```  
  
 La primera versión de `WriteFormattedDocComment()` asignaba una matriz, varias subcadenas y una subcadena recortada junto con una matriz `params` vacía. También se ha comprobado "///". El código revisado solo usa la indización y no realiza ninguna asignación. Busca el primer carácter que no sea un espacio en blanco y, a continuación, comprueba el carácter carácter a carácter para ver si la cadena comienza con "///". El nuevo código usa en `IndexOfFirstNonWhiteSpaceChar` lugar de <xref:System.String.TrimStart%2A> para devolver el primer índice (después de un índice de inicio especificado) en el que se produce un carácter que no es un espacio en blanco. La corrección no está completa, pero sirve para comprobar cómo se aplican correcciones similares para obtener una solución completa. Al aplicar este enfoque en todo el código, se pueden quitar todas las asignaciones en `WriteFormattedDocComment()`.
  
 **Ejemplo 4: StringBuilder**  
  
 En este ejemplo se usa un objeto <xref:System.Text.StringBuilder>. La función siguiente genera un nombre de tipo completo para tipos genéricos:  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 El foco está en la línea que crea una nueva instancia <xref:System.Text.StringBuilder>. El código causa una asignación para `sb.ToString()` y asignaciones internas dentro de la implementación <xref:System.Text.StringBuilder>, pero esas asignaciones no se pueden controlar si se desea el resultado de la cadena.
  
 **Corrección para el ejemplo 4**  
  
 Para corregir la asignación del objeto `StringBuilder`, almacene el objeto en la memoria caché. El almacenamiento en caché de una única instancia que podría desecharse puede mejorar el rendimiento de manera significativa. Esta es la nueva implementación de la función, que omite todo el código excepto las nuevas líneas primera y última:  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 Las partes clave son las nuevas funciones `AcquireBuilder()` y `GetStringAndReleaseBuilder()`:  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 Dado que los nuevos compiladores usan subprocesos, estas implementaciones utilizan un campo estático de subproceso (atributo <xref:System.ThreadStaticAttribute>) para almacenar en la caché el <xref:System.Text.StringBuilder>, con lo que probablemente se pueda renunciar a la declaración `ThreadStatic`. El campo estático de subproceso contiene un valor único para cada subproceso que ejecuta este código.
  
 `AcquireBuilder()` devuelve la instancia <xref:System.Text.StringBuilder> almacenada en la caché (si la hay) después de borrarla y establecer el campo o la caché en null. De lo contrario, `AcquireBuilder()` crea una instancia nueva y la devuelve, dejando el campo o la caché establecidos en null.
  
 Cuando haya acabado con <xref:System.Text.StringBuilder>, llame a `GetStringAndReleaseBuilder()` para obtener el resultado de la cadena, guarde la instancia <xref:System.Text.StringBuilder> en el campo o en la caché, y después devuelva el resultado. Es posible que en la ejecución se vuelva a introducir este código y se creen varios objetos <xref:System.Text.StringBuilder> (aunque rara vez ocurre). El código solo guarda la última instancia <xref:System.Text.StringBuilder> liberada para su uso posterior. Esa sencilla estrategia de almacenamiento en caché redujo significativamente las asignaciones en los nuevos compiladores. Hay partes de .NET Framework y MSBuild ("MSBuild") que usan una técnica similar para mejorar el rendimiento.
  
 Esta estrategia simple de almacenamiento en caché respeta el buen diseño de caché porque tiene un límite de tamaño. No obstante, hay más código ahora que en el original, lo que significa un mayor coste de mantenimiento. Únicamente debe adoptar la estrategia de almacenamiento en caché si se ha encontrado con un problema de rendimiento y PerfView muestra que las asignaciones de <xref:System.Text.StringBuilder> suponen una contribución significativa.
  
### <a name="linq-and-lambdas"></a>LINQ y lambdas  
Language-Integrated Query (LINQ), junto con las expresiones lambda, es un ejemplo de una característica de productividad. Sin embargo, su uso puede tener un impacto significativo en el rendimiento a lo largo del tiempo, y es posible que tenga que volver a escribir el código.
  
 **Ejemplo 5: lambdas, List \<T> e IEnumerable\<T>**  
  
 En este ejemplo se usa [LINQ y código de estilo funcional](/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) para buscar un símbolo en el modelo del compilador, dada una cadena de nombre:  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 El nuevo compilador y las experiencias de IDE creadas en él llaman a `FindMatchingSymbol()` con mucha frecuencia, y hay varias asignaciones ocultas en la única línea de código de esta función. Para examinar estas asignaciones, primero divida la única línea de código de la función en dos líneas:  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 En la primera línea, la [expresión lambda](../../csharp/language-reference/operators/lambda-expressions.md) `s => s.Name == name` [cierra](/archive/blogs/ericlippert/what-are-closures) la variable local `name`. Esto significa que, además de asignar un objeto para el [delegado](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) que contiene `predicate`, el código asigna una clase estática para contener el entorno que captura el valor de `name`. El compilador genera código como el siguiente:  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 Las dos asignaciones `new` (una para la clase de entorno y la otra para el delegado) son ahora explícitas.
  
 Ahora observe la llamada a `FirstOrDefault`. Este método de extensión en el tipo <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> también crea una asignación. Dado que `FirstOrDefault` toma un objeto <xref:System.Collections.Generic.IEnumerable%601> como primer argumento, se puede expandir la llamada al código siguiente (un poco simplificado para el análisis):  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ...
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 La variable `symbols` tiene el tipo <xref:System.Collections.Generic.List%601>. El tipo de colección <xref:System.Collections.Generic.List%601> implementa <xref:System.Collections.Generic.IEnumerable%601> y define inteligentemente un enumerador (interfaz <xref:System.Collections.Generic.IEnumerator%601>) que <xref:System.Collections.Generic.List%601> implementa con una `struct`. Usar una estructura en vez de una clase significa que normalmente se evitan asignaciones del montón, lo que, a su vez, puede afectar al rendimiento de la recolección de elementos no utilizados.  Por lo general, los enumeradores se usan con el bucle `foreach` del lenguaje, que utiliza la estructura de enumerador tal como se devuelve en la pila de llamadas. El incremento del puntero de la pila de llamadas para dejar sitio a un objeto no afecta a GC del modo que lo hace una asignación del montón.
  
 En el caso de la llamada `FirstOrDefault` expandida, el código necesita llamar a `GetEnumerator()` en una interfaz <xref:System.Collections.Generic.IEnumerable%601>. Con la asignación de `symbols` a la variable `enumerable` de tipo `IEnumerable<Symbol>`, se pierde la información de que el objeto real es una lista <xref:System.Collections.Generic.List%601>. Esto significa que cuando el código captura al enumerador con `enumerable.GetEnumerator()`, .NET Framework tiene que realizar una conversión boxing de la estructura devuelta para asignarla a la variable `enumerator`.
  
 **Corrección para el ejemplo 5**  
  
 En esta corrección, `FindMatchingSymbol` se reescribe para reemplazar la única línea de código con seis líneas de código que siguen siendo concisas, fáciles de leer y entender, y sencillas de mantener:  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 El código no utiliza métodos de extensión LINQ, lambdas ni enumeradores, y no crea asignaciones. No hay asignaciones porque el compilador puede ver que la colección `symbols` es una <xref:System.Collections.Generic.List%601> y puede vincular el enumerador resultante (una estructura) a una variable local con el tipo correcto para evitar la conversión boxing. La versión original de esta función es un gran ejemplo del poder expresivo de C# y de la productividad .NET Framework. Esta nueva y más eficaz versión conserva esas cualidades sin agregar ningún código complejo que haya que mantener.
  
### <a name="async-method-caching"></a>Almacenamiento en caché del método asincrónico  

En el ejemplo siguiente se muestra un problema común al intentar usar resultados de la caché en un método [async](../../csharp/programming-guide/concepts/async/index.md).
  
 **Ejemplo 6: almacenamiento en caché en métodos asincrónicos**  
  
 Las características del IDE de Visual Studio incorporadas a los nuevos compiladores de C# y Visual Basic suelen capturar árboles de sintaxis y, cuando eso sucede, los compiladores usan asincronía para que Visual Studio siga respondiendo. Esta es la primera versión del código que puede escribir para obtener un árbol de sintaxis:  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 Como se puede ver, la llamada a `GetSyntaxTreeAsync()` crea una instancia de `Parser`, analiza el código y luego devuelve un objeto <xref:System.Threading.Tasks.Task>, `Task<SyntaxTree>`. La parte costosa es asignar la instancia `Parser` y analizar el código. La función devuelve <xref:System.Threading.Tasks.Task>, de modo que los autores de llamadas pueden esperar al trabajo de análisis y liberar el subproceso de la interfaz de usuario para que responda a la entrada del usuario.
  
 Hay varias características de Visual Studio que pueden intentar obtener el mismo árbol de sintaxis; por tanto, se puede escribir el código siguiente para almacenar en caché el resultado del análisis a fin de ahorrar tiempo y asignaciones. No obstante, este código crea una asignación:  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 Como puede ver, el nuevo código con almacenamiento en caché tiene un campo `SyntaxTree` denominado `cachedResult`. Cuando este campo es null, `GetSyntaxTreeAsync()` hace el trabajo y guarda el resultado en la caché. `GetSyntaxTreeAsync()` devuelve el objeto `SyntaxTree`. El problema es que cuando se tiene una función `async` de tipo `Task<SyntaxTree>`, y se devuelve un valor de tipo `SyntaxTree`, el compilador emite código para asignar una tarea que contenga el resultado (mediante `Task<SyntaxTree>.FromResult()`). La tarea se marca como completada y el resultado está disponible de inmediato. En el código de los nuevos compiladores, la aparición de objetos <xref:System.Threading.Tasks.Task> que ya se habían completado se producía tan a menudo que corregir estas asignaciones mejoró sensiblemente la respuesta.
  
 **Corrección para el ejemplo 6**  
  
 Para quitar la asignación completada <xref:System.Threading.Tasks.Task> , puede almacenar en caché el objeto de tarea con el resultado completado:  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 Este código cambia el tipo de `cachedResult` a `Task<SyntaxTree>` y emplea una función del asistente `async` que contiene el código original de `GetSyntaxTreeAsync()`. `GetSyntaxTreeAsync()` ahora usa el [operador de uso combinado de NULL](../../csharp/language-reference/operators/null-coalescing-operator.md) para devolver `cachedResult` si no es null. Si `cachedResult` es null, entonces `GetSyntaxTreeAsync()` llama a `GetSyntaxTreeUncachedAsync()` y almacena el resultado en la caché. Observe que `GetSyntaxTreeAsync()` no aguarda por la llamada a `GetSyntaxTreeUncachedAsync()`, como haría el código normalmente. No usar await significa que cuando `GetSyntaxTreeUncachedAsync()` devuelve su objeto <xref:System.Threading.Tasks.Task>, `GetSyntaxTreeAsync()` devuelve inmediatamente <xref:System.Threading.Tasks.Task>. Ahora, el resultado almacenado en la caché es <xref:System.Threading.Tasks.Task>, por lo que no hay asignaciones que devolver el resultado almacenado en la caché.
  
### <a name="additional-considerations"></a>Consideraciones adicionales  
 A continuación se señalan otras cuestiones sobre aplicaciones grandes o que procesan una gran cantidad de datos.
  
 **Diccionarios**  
  
 Los diccionarios son omnipresentes en muchos programas: resultan muy prácticos y son eficaces de manera inherente. Sin embargo, a menudo se usa de forma inapropiada. En Visual Studio y los nuevos compiladores, el análisis muestra que muchos de los diccionarios de los diccionarios contienen un único elemento o están vacíos. Un <xref:System.Collections.Generic.Dictionary%602> vacío tiene diez campos y ocupa 48 bytes en el montón de una máquina x86. Los diccionarios son estupendos cuando se necesita una asignación o una estructura de datos asociativa con una búsqueda constante. No obstante, cuando solo se tienen unos pocos elementos, el usar un diccionario es una pérdida de espacio. En su lugar, por ejemplo, se puede realizar una búsqueda iterativa por un `List<KeyValuePair\<K,V>>` sin perder velocidad. Si usa un diccionario solo para cargarlo con datos y luego leerlos (un modelo muy común), usar una matriz ordenada con una búsqueda N(log(N)) puede resultar casi tan rápido, en función del número de elementos que se use.
  
 **Clases frente a estructuras**  
  
 En cierto modo, las clases y las estructuras ofrecen la clásica contrapartida entre espacio y tiempo a la hora de para ajustar las aplicaciones. Las clases generan 12 bytes de sobrecarga en una máquina x86 aunque no tengan campos, pero pasarlas no resulta costoso ya que solo se necesita un puntero para hacer referencia a una instancia de clase. Las estructuras no crean asignaciones del montón si no se les aplica una conversión boxing, pero cuando se pasan estructuras grandes como argumentos de función o valores devueltos, se consume tiempo de CPU para copiar atómicamente todos los miembros de datos de las estructuras. Controle las llamadas repetidas a propiedades que devuelvan estructuras y almacene en la caché el valor de la propiedad en una variable local para evitar el exceso de copia de datos.
  
 **Cachés**  
  
 Un truco de rendimiento muy habitual es almacenar los resultados en la caché. Sin embargo, una caché sin un límite de tamaño o una directiva de retirada puede conllevar la pérdida de memoria. Si para procesar grandes cantidades de datos usa mucha memoria en las cachés, puede causar que la recolección de elementos no utilizados anule los beneficios de las búsquedas de la caché.
  
 En este artículo se ha explicado cómo deben tenerse en cuenta los síntomas de cuello de botella de rendimiento que pueden afectar a la respuesta de su aplicación, especialmente en sistemas grandes o sistemas que procesan una gran cantidad de datos. Los causantes más habituales son la conversión boxing, las manipulaciones de cadenas, LINQ y lambda, el almacenamiento en caché en métodos asincrónicos, el uso de la memoria caché sin un límite de tamaño o directiva de retirada, la utilización inadecuada de diccionarios y el pase de estructuras.es. No olvide los cuatro hechos sobre el ajuste de las aplicaciones:  
  
- No optimice prematuramente: sea productivo y ajuste la aplicación cuando detecte problemas.
  
- Los perfiles no mienten: si no mide, conjetura.
  
- Unas herramientas buenas marcan la diferencia: descargue PerfView y pruébelo.
  
- La clave son las asignaciones: es donde el equipo de la plataforma de compiladores invirtió más tiempo en mejorar el rendimiento de los nuevos compiladores.
  
## <a name="see-also"></a>Vea también

- [Vídeo de presentación de este tema](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)
- [Guía básica para la generación de perfiles de rendimiento](/visualstudio/profiling/beginners-guide-to-performance-profiling)
- [Rendimiento](index.md)
- [.NET Performance Tips (Sugerencias de rendimiento de .NET)](/previous-versions/dotnet/articles/ms973839(v=msdn.10))
- [Tutoriales de PerfView de Channel 9](https://channel9.msdn.com/Series/PerfView-Tutorial)
- [SDK de .NET Compiler Platform](../../csharp/roslyn-sdk/index.md)
- [repositorio dotnet/Roslyn en GitHub](https://github.com/dotnet/roslyn)
