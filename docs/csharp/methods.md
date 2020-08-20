---
title: 'Métodos: Guía de C#'
description: Información general sobre métodos, parámetros de método y valores devueltos de método
ms.technology: csharp-fundamentals
ms.date: 05/21/2018
ms.assetid: 577a8527-1081-4b36-9b9e-0685b6553c6e
ms.openlocfilehash: 09a287b3d74e1b8dbdaf4a53cb207dfe1fad8a0c
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063359"
---
# <a name="methods"></a>Métodos

Un método es un bloque de código que contiene una serie de instrucciones. Un programa hace que se ejecuten las instrucciones al llamar al método y especificando los argumentos de método necesarios. En C#, todas las instrucciones ejecutadas se realizan en el contexto de un método. El método `Main` es el punto de entrada para cada aplicación de C# y se llama mediante Common Language Runtime (CLR) cuando se inicia el programa.

> [!NOTE]
> En este tema se analizan los métodos denominados. Para obtener información sobre las funciones anónimas, vea [Funciones anónimas](programming-guide/statements-expressions-operators/anonymous-functions.md).

<a name="signatures"></a>

## <a name="method-signatures"></a>Firmas de método

Los métodos se declaran en una `class` o `struct` al especificar:

- Un nivel de acceso opcional, como, por ejemplo, `public` o `private`. De manera predeterminada, es `private`.
- Modificadores opcionales, como, por ejemplo, `abstract` o `sealed`.
- El valor devuelto o, si el método no tiene ninguno, `void`.
- El nombre del método.
- Los parámetros del método. Los parámetros de método se encierran entre paréntesis y se separan por comas. Los paréntesis vacíos indican que el método no requiere parámetros.

Todas estas partes forman la firma del método.

> [!NOTE]
> Un tipo de valor devuelto de un método no forma parte de la firma del método con el objetivo de sobrecargar el método. Sin embargo, forma parte de la firma del método al determinar la compatibilidad entre un delegado y el método que señala.

En el siguiente ejemplo se define una clase denominada `Motorcycle` que contiene cinco métodos:

[!code-csharp[csSnippets.Methods#40](../../samples/snippets/csharp/concepts/methods/methods40.cs#40)]

Tenga en cuenta que la clase `Motorcycle` incluye un método sobrecargado, `Drive`. Dos métodos tienen el mismo nombre, pero se deben diferenciar en sus tipos de parámetros.

<a name="invocation"></a>

## <a name="method-invocation"></a>Invocación de método

Los métodos pueden ser de *instancia* o *estáticos*. Para invocar un método de instancia es necesario crear una instancia de un objeto y llamar al método del objeto; el método de una instancia actúa en dicha instancia y sus datos. Si quiere invocar un método estático, haga referencia al nombre del tipo al que pertenece el método; los métodos estáticos no actúan en datos de instancia. Al intentar llamar a un método estático mediante una instancia de objeto se genera un error del compilador.

Llamar a un método es como acceder a un campo. Después del nombre de objeto (si se llama a un método de instancia) o el nombre de tipo (si llama a un método `static`), agregue un punto, el nombre del método y paréntesis. Los argumentos se enumeran entre paréntesis y están separados por comas.

La definición del método especifica los nombres y tipos de todos los parámetros necesarios. Cuando un autor de llamada invoca el método, proporciona valores concretos denominados argumentos para cada parámetro. Los argumentos deben ser compatibles con el tipo de parámetro, pero el nombre de argumento, si se usa alguno en el código de llamada, no tiene que ser el mismo que el del parámetro con nombre definido en el método. En el ejemplo siguiente, el método `Square` incluye un parámetro único de tipo `int` denominado *i*. La primera llamada de método pasa al método `Square` una variable de tipo `int` denominada *num*; la segunda, una constante numérica; y la tercera, una expresión.

[!code-csharp[csSnippets.Methods#74](../../samples/snippets/csharp/concepts/methods/params74.cs#74)]

La forma más común de invocación de método usa argumentos posicionales; proporciona argumentos en el mismo orden que los parámetros de método. Los métodos de la clase `Motorcycle` se pueden llamar como en el ejemplo siguiente. Por ejemplo, la llamada al método `Drive` incluye dos argumentos que se corresponden con los dos parámetros de la sintaxis del método. El primero se convierte en el valor del parámetro `miles` y el segundo en el valor del parámetro `speed`.

[!code-csharp[csSnippets.Methods#41](../../samples/snippets/csharp/concepts/methods/methods40.cs#41)]

También se pueden usar *argumentos con nombre* en lugar de argumentos posicionales al invocar un método. Cuando se usan argumentos con nombre, el nombre del parámetro se especifica seguido de dos puntos (":") y el argumento. Los argumentos del método pueden aparecer en cualquier orden, siempre que todos los argumentos necesarios están presentes. En el ejemplo siguiente se usan argumentos con nombre para invocar el método `TestMotorcycle.Drive`. En este ejemplo, los argumentos con nombre se pasan en orden inverso desde la lista de parámetros del método.

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/named1.cs#45)]

Un método se puede invocar con argumentos posicionales y argumentos con nombre. Pero un argumento posicional no puede seguir a un argumento con nombre. En el ejemplo siguiente se invoca el método `TestMotorcycle.Drive` del ejemplo anterior con un argumento posicional y un argumento con nombre.

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/named2.cs#46)]

<a name="inherited"></a>

## <a name="inherited-and-overridden-methods"></a>Métodos heredados e invalidados

Además de los miembros que se definen explícitamente en un tipo, un tipo hereda miembros definidos en sus clases base. Dado que todos los tipos en el sistema de tipo administrado heredan directa o indirectamente de la clase <xref:System.Object>, todos los tipos heredan sus miembros, como <xref:System.Object.Equals(System.Object)>, <xref:System.Object.GetType> y <xref:System.Object.ToString>. En el ejemplo siguiente se define una clase `Person`, se crean instancias de dos objetos `Person` y se llama al método `Person.Equals` para determinar si los dos objetos son iguales. Pero el método `Equals` no está definido en la clase `Person`; se hereda de <xref:System.Object>.

[!code-csharp[csSnippets.Methods#104](../../samples/snippets/csharp/concepts/methods/inherited1.cs#104)]

Los tipos pueden invalidar miembros heredados usando la palabra clave `override` y proporcionando una implementación para el método invalidado. La firma del método debe ser igual a la del método invalidado. El ejemplo siguiente es similar al anterior, salvo que invalida el método <xref:System.Object.Equals(System.Object)>. (También invalida el método <xref:System.Object.GetHashCode>, ya que los dos métodos están diseñados para proporcionar resultados coherentes).

[!code-csharp[csSnippets.Methods#105](../../samples/snippets/csharp/concepts/methods/overridden1.cs#105)]

<a name="passing"></a>

## <a name="passing-parameters"></a>Pasar parámetros

Todos los tipos de C# son *tipos de valor* o *tipos de referencia*. Para obtener una lista de tipos de valor integrados, vea [Tipos](./tour-of-csharp/types.md). De forma predeterminada, los tipos de valor y los tipos de referencia se pasan a un método por valor.

<a name="byval"></a>

### <a name="passing-parameters-by-value"></a>Pasar parámetros por valor

Cuando un tipo de valor se pasa a un método por valor, se pasa una copia del objeto y no el propio objeto. Por lo tanto, los cambios realizados en el objeto en el método llamado no tienen ningún efecto en el objeto original cuando el control vuelve al autor de la llamada.

En el ejemplo siguiente se pasa un tipo de valor a un método por valor, y el método llamado intenta cambiar el valor del tipo de valor. Define una variable de tipo `int`, que es un tipo de valor, inicializa su valor en 20 y lo pasa a un método denominado `ModifyValue` que cambia el valor de la variable a 30. Pero cuando el método vuelve, el valor de la variable no cambia.

[!code-csharp[csSnippets.Methods#10](../../samples/snippets/csharp/concepts/methods/byvalue10.cs#10)]

Cuando un objeto de un tipo de referencia se pasa a un método por valor, se pasa por valor una referencia al objeto. Es decir, el método no recibe el objeto concreto, sino un argumento que indica la ubicación del objeto. Si cambia un miembro del objeto mediante esta referencia, el cambio se reflejará en el objeto cuando el control vuelva al método de llamada. Pero el reemplazo del objeto pasado al método no tendrá ningún efecto en el objeto original cuando el control vuelva al autor de la llamada.

En el ejemplo siguiente se define una clase (que es un tipo de referencia) denominada `SampleRefType`. Crea una instancia de un objeto `SampleRefType`, asigna 44 a su campo `value` y pasa el objeto al método `ModifyObject`. Fundamentalmente, este ejemplo hace lo mismo que el ejemplo anterior: pasa un argumento por valor a un método. Pero, debido a que se usa un tipo de referencia, el resultado es diferente. La modificación que se lleva a cabo en `ModifyObject` para el campo `obj.value` cambia también el campo `value` del argumento, `rt`, en el método `Main` a 33, tal y como muestra el resultado del ejemplo.

[!code-csharp[csSnippets.Methods#42](../../samples/snippets/csharp/concepts/methods/byvalue42.cs#42)]

<a name="byref"></a>

### <a name="passing-parameters-by-reference"></a>Pasar parámetros por referencia

Pase un parámetro por referencia cuando quiera cambiar el valor de un argumento en un método y reflejar ese cambio cuando el control vuelva al método de llamada. Para pasar un parámetro por referencia, use la palabra clave [`ref`](language-reference/keywords/ref.md) o [`out`](language-reference/keywords/out-parameter-modifier.md). También puede pasar un valor por referencia para evitar la copia, pero impedir modificaciones igualmente usando la palabra clave [`in`](language-reference/keywords/in-parameter-modifier.md).

El ejemplo siguiente es idéntico al anterior, salvo que el valor se pasa por referencia al método `ModifyValue`. Cuando se modifica el valor del parámetro en el método `ModifyValue`, el cambio del valor se refleja cuando el control vuelve al autor de la llamada.

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/byref106.cs#106)]

Un patrón común que se usa en parámetros ref implica intercambiar los valores de variables. Se pasan dos variables a un método por referencia y el método intercambia su contenido. En el ejemplo siguiente se intercambian valores enteros.

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/swap107.cs#107)]

Pasar un parámetro de tipo de referencia le permite cambiar el valor de la propia referencia, en lugar del valor de sus campos o elementos individuales.

<a name="paramarray"></a>

### <a name="parameter-arrays"></a>Matrices de parámetros

A veces, el requisito de especificar el número exacto de argumentos al método es restrictivo. El uso de la palabra clave `params` para indicar que un parámetro es una matriz de parámetros permite llamar al método con un número variable de argumentos. El parámetro etiquetado con la palabra clave `params` debe ser un tipo de matriz y ser el último parámetro en la lista de parámetros del método.

Un autor de llamada puede luego invocar el método de una de las tres maneras siguientes:

- Si se pasa una matriz del tipo adecuado que contenga el número de elementos que se quiera.
- Si se pasa una lista separada por comas de los argumentos individuales del tipo adecuado para el método.
- Si no se proporciona un argumento a la matriz de parámetros.

En el ejemplo siguiente se define un método denominado `GetVowels` que devuelve todas las vocales de una matriz de parámetros. El método `Main` muestra las tres formas de invocar el método. Los autores de llamadas no deben proporcionar argumentos para los parámetros que incluyen el modificador `params`. En ese caso, el parámetro es `null`.

[!code-csharp[csSnippets.Methods#75](~/samples/snippets/csharp/concepts/methods/params75.cs#75)]

<a name="optional"></a>

## <a name="optional-parameters-and-arguments"></a>Argumentos y parámetros opcionales

La definición de un método puede especificar que sus parámetros son necesarios o que son opcionales. Los parámetros son necesarios de forma predeterminada. Para especificar parámetros opcionales se incluye el valor predeterminado del parámetro en la definición del método. Cuando se llama al método, si no se proporciona ningún argumento para un parámetro opcional, se usa el valor predeterminado.

El valor predeterminado del parámetro debe asignarse con uno de los siguientes tipos de expresiones:

- Una constante, como una cadena literal o un número.
- Una expresión con el formato `new ValType()`, donde `ValType` es un tipo de valor. Tenga en cuenta que esta acción invoca el constructor sin parámetros implícito del tipo de valor, que no es un miembro real del tipo.
- Una expresión con el formato `default(ValType)`, donde `ValType` es un tipo de valor.

Si un método incluye parámetros necesarios y opcionales, los parámetros opcionales se definen al final de la lista de parámetros, después de todos los parámetros necesarios.

En el ejemplo siguiente se define un método, `ExampleMethod`, que tiene un parámetro necesario y dos opcionales.

[!code-csharp[csSnippets.Methods#21](../../samples/snippets/csharp/concepts/methods/optional1.cs#21)]

Si se invoca un método con varios argumentos opcionales mediante argumentos posicionales, el autor de la llamada debe proporcionar un argumento para todos los parámetros opcionales, del primero al último, a los que se proporcione un argumento. Por ejemplo, en el caso del método `ExampleMethod`, si el autor de la llamada proporciona un argumento para el parámetro `description`, también debe proporcionar uno para el parámetro `optionalInt`. `opt.ExampleMethod(2, 2, "Addition of 2 and 2");` es una llamada de método válida; `opt.ExampleMethod(2, , "Addition of 2 and 0");` genera un error del compilador, "Falta un argumento".

Si se llama a un método mediante argumentos con nombre o una combinación de argumentos posicionales y con nombre, el autor de la llamada puede omitir los argumentos que siguen al último argumento posicional en la llamada al método.

En el ejemplo siguiente se llama tres veces al método `ExampleMethod`.  Las dos primeras llamadas al método usan argumentos posicionales. La primera omite los dos argumentos opcionales, mientras que la segunda omite el último argumento. La tercera llamada al método proporciona un argumento posicional para el parámetro necesario, pero usa un argumento con nombre para proporcionar un valor al parámetro `description` mientras omite el argumento `optionalInt`.

[!code-csharp[csSnippets.Methods#22](../../samples/snippets/csharp/concepts/methods/optional1.cs#22)]

El uso de parámetros opcionales incide en la *resolución de sobrecarga* o en la manera en que el compilador de C# determina qué sobrecarga en particular debe invocar una llamada al método, como sigue:

- Un método, indexador o constructor es un candidato para la ejecución si cada uno de sus parámetros es opcional o corresponde, por nombre o por posición, a un solo argumento de la instrucción de llamada y el argumento se puede convertir al tipo del parámetro.
- Si se encuentra más de un candidato, se aplican las reglas de resolución de sobrecarga de las conversiones preferidas a los argumentos que se especifican explícitamente. Los argumentos omitidos en parámetros opcionales se ignoran.
- Si dos candidatos se consideran igualmente correctos, la preferencia pasa a un candidato que no tenga parámetros opcionales cuyos argumentos se hayan omitido en la llamada. Se trata de una consecuencia de una preferencia general en la resolución de sobrecarga para los candidatos con menos parámetros.

<a name="return"></a>

## <a name="return-values"></a>Valores devueltos

Los métodos pueden devolver un valor al autor de llamada. Si el tipo de valor devuelto (el tipo que aparece antes del nombre de método) no es `void`, el método puede devolver el valor mediante la palabra clave `return`. Una instrucción con la palabra clave `return` seguida de una variable, una constante o una expresión que coincide con el tipo de valor devuelto devolverá este valor al autor de la llamada al método. Los métodos con un tipo de valor devuelto no nulo son necesarios para usar la palabra clave `return` para devolver un valor. La palabra clave `return` también detiene la ejecución del método.

Si el tipo de valor devuelto es `void`, una instrucción `return` sin un valor también es útil para detener la ejecución del método. Sin la palabra clave `return` , el método dejará de ejecutarse cuando alcance el final del bloque de código.

Por ejemplo, estos dos métodos utilizan la palabra clave `return` para devolver enteros:

[!code-csharp[csSnippets.Methods#44](../../samples/snippets/csharp/concepts/methods/return44.cs#44)]

Para utilizar un valor devuelto de un método, el método de llamada puede usar la llamada de método en cualquier lugar; un valor del mismo tipo sería suficiente. También puede asignar el valor devuelto a una variable. Por ejemplo, los dos siguientes ejemplos de código logran el mismo objetivo:

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/return44.cs#45)]

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/return44.cs#46)]

Usar una variable local, en este caso, `result`, para almacenar un valor es opcional. La legibilidad del código puede ser útil, o puede ser necesaria si debe almacenar el valor original del argumento para todo el ámbito del método.

A veces, quiere que el método devuelva más que un solo valor. A partir de C# 7.0, puede hacer esto fácilmente mediante *tipos de tupla* y *literales de tupla*. El tipo de tupla define los tipos de datos de los elementos de la tupla. Los literales de tupla proporcionan los valores reales de la tupla devuelta. En el ejemplo siguiente, `(string, string, string, int)` define el tipo de tupla que devuelve el método `GetPersonalInfo`. La expresión `(per.FirstName, per.MiddleName, per.LastName, per.Age)` es el literal de tupla; el método devuelve el nombre, los apellidos y la edad de un objeto `PersonInfo`.

```csharp
public (string, string, string, int) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    return (per.FirstName, per.MiddleName, per.LastName, per.Age);
}
```

Luego, el autor de la llamada puede usar la tupla devuelta con código como el siguiente:

```csharp
var person = GetPersonalInfo("111111111")
Console.WriteLine("{person.Item1} {person.Item3}: age = {person.Item4}");
```

También se pueden asignar nombres a los elementos de tupla en la definición de tipo de tupla. En el ejemplo siguiente se muestra una versión alternativa del método `GetPersonalInfo` que usa elementos con nombre:

```csharp
public (string FName, string MName, string LName, int Age) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    return (per.FirstName, per.MiddleName, per.LastName, per.Age);
}
```

La llamada anterior al método `GetPersonInfo` se puede modificar luego de la manera siguiente:

```csharp
var person = GetPersonalInfo("111111111");
Console.WriteLine("{person.FName} {person.LName}: age = {person.Age}");
```

Si a un método se pasa una matriz como argumento y modifica el valor de elementos individuales, no es necesario que el método devuelva la matriz, aunque puede que se prefiera hacerlo a efectos del buen estilo o el flujo funcional de valores.  Esto se debe a que C# pasa todos los tipos de referencia por valor, y el valor de una referencia a la matriz es el puntero a la matriz. En el ejemplo siguiente, los cambios al contenido de la matriz `values` que se realizan en el método `DoubleValues` los puede observar cualquier código que tenga una referencia a la matriz.

[!code-csharp[csSnippets.Methods#101](../../samples/snippets/csharp/concepts/methods/returnarray1.cs#101)]

<a name="extension"></a>

## <a name="extension-methods"></a>Métodos de extensión

Normalmente, hay dos maneras de agregar un método a un tipo existente:

- Modificar el código fuente del tipo. No puede hacerlo si no es propietario del código fuente del tipo. Y esto supone un cambio sustancial si también agrega los campos de datos privados para admitir el método.
- Definir el nuevo método en una clase derivada. No se puede agregar un método de este modo con herencia para otros tipos, como estructuras y enumeraciones. Tampoco se puede usar para agregar un método a una clase sealed.

Los métodos de extensión permiten agregar un método a un tipo existente sin modificar el propio tipo o implementar el nuevo método en un tipo heredado. El método de extensión tampoco tiene que residir en el mismo ensamblado que el tipo que extiende. Llame a un método de extensión como si fuera miembro de un tipo definido.

Para obtener más información, vea [Métodos de extensión](programming-guide/classes-and-structs/extension-methods.md).

<a name="async"></a>

## <a name="async-methods"></a>Métodos asincrónicos

Mediante la característica asincrónica, puede invocar métodos asincrónicos sin usar definiciones de llamada explícitas ni dividir manualmente el código en varios métodos o expresiones lambda.

Si marca un método con el modificador [async](language-reference/keywords/async.md), puede usar el operador [await](language-reference/operators/await.md) en el método. Cuando el control llega a una expresión `await` en el método asincrónico, el control se devuelve al autor de la llamada si la tarea en espera no se ha completado y se suspende el progreso del método con la palabra clave `await` hasta que dicha tarea se complete. Cuando se completa la tarea, la ejecución puede reanudarse en el método.

> [!NOTE]
> Un método asincrónico vuelve al autor de llamada cuando encuentra el primer objeto esperado que aún no se ha completado o cuando llega al final del método asincrónico, lo que ocurra primero.

Un método asincrónico puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> o `void`. El tipo de valor devuelto `void` se usa principalmente para definir controladores de eventos, donde se requiere un tipo de valor devuelto `void`. No se puede esperar un método asincrónico que devuelve `void` y el autor de llamada a un método que no devuelve ningún valor no puede capturar ninguna excepción producida por este. A partir de la versión C# 7.0, el método asincrónico puede tener [cualquier tipo de valor devuelto similar a una tarea ](./whats-new/csharp-7.md#generalized-async-return-types).

En el ejemplo siguiente, `DelayAsync` es un método asincrónico que contiene una instrucción return que devuelve un entero. Como se trata de un método asincrónico, su declaración de método debe tener un tipo de valor devuelto de `Task<int>`. Dado que el tipo de valor devuelto es `Task<int>`, la evaluación de la expresión `await` en `DoSomethingAsync` genera un entero, como se demuestra en la instrucción `int result = await delayTask` siguiente.

[!code-csharp[csSnippets.Methods#102](../../samples/snippets/csharp/concepts/methods/async1.cs#102)]

Un método asincrónico no puede declarar ningún parámetro [in](language-reference/keywords/in-parameter-modifier.md), [ref](language-reference/keywords/ref.md) o [out](language-reference/keywords/out-parameter-modifier.md), pero puede llamar a los métodos que tienen estos parámetros.

 Para obtener más información sobre los métodos asincrónicos, vea [Programación asincrónica con Async y Await](async.md), [Controlar el flujo en los programas asincrónicos](programming-guide/concepts/async/control-flow-in-async-programs.md) y [Tipos de valor devueltos asincrónicos](programming-guide/concepts/async/async-return-types.md).

<a name="expr"></a>

## <a name="expression-bodied-members"></a>Miembros con forma de expresión

Es habitual tener definiciones de método que simplemente hacen las devoluciones de forma inmediata con el resultado de una expresión, o que tienen una sola instrucción como cuerpo del método.  Hay un acceso directo de sintaxis para definir este método mediante `=>`:

```csharp
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);
public void Print() => Console.WriteLine(First + " " + Last);
// Works with operators, properties, and indexers too.
public static Complex operator +(Complex a, Complex b) => a.Add(b);
public string Name => First + " " + Last;
public Customer this[long id] => store.LookupCustomer(id);
```

Si el método devuelve `void` o se trata de un método asincrónico, el cuerpo del método debe ser una expresión de instrucción (igual que con las expresiones lambda).  Para propiedades e indexadores, deben ser de solo lectura, y no se usa la palabra clave de descriptor de acceso `get`.

<a name="iterators"></a>

## <a name="iterators"></a>Iterators

Un iterador realiza una iteración personalizada en una colección, como una lista o matriz. Un iterador utiliza la instrucción [yield return](language-reference/keywords/yield.md) para devolver cada elemento de uno en uno. Cuando se llega a una instrucción `yield return`, se recuerda la ubicación actual para que el autor de la llamada pueda solicitar el siguiente elemento en la secuencia.

El tipo de valor devuelto de un iterador puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

Para obtener más información, consulta [Iteradores](programming-guide/concepts/iterators.md).

## <a name="see-also"></a>Consulte también

- [Modificadores de acceso](language-reference/keywords/access-modifiers.md)
- [Clases estáticas y sus miembros](programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [Herencia](programming-guide/classes-and-structs/inheritance.md)
- [Clases y miembros de clase abstractos y sellados](programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [params](language-reference/keywords/params.md)
- [out](language-reference/keywords/out-parameter-modifier.md)
- [ref](language-reference/keywords/ref.md)
- [in](language-reference/keywords/in-parameter-modifier.md)
- [Pasar parámetros](programming-guide/classes-and-structs/passing-parameters.md)
