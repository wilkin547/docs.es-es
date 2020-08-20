---
title: Bloques de creación de "programas" de C#
description: Obtenga información sobre miembros, expresiones e instrucciones de C#. Los tipos contienen miembros que se escriben. Estos miembros se crean a partir de instrucciones y expresiones.
ms.date: 08/06/2020
ms.openlocfilehash: 142fe7b5a3424a8925638bfb4e4437392347f4c6
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268145"
---
# <a name="program-building-blocks"></a>Bloques de creación de programas

Los tipos descritos en el artículo anterior se compilan con estos bloques de creación: [***miembros***](../programming-guide/classes-and-structs/members.md), [***expresiones*** e ***instrucciones***](../programming-guide/statements-expressions-operators/index.md).

## <a name="members"></a>Miembros

Los miembros de una `class` son ***estáticos*** o ***de instancia***. Los miembros estáticos pertenecen a clases y los miembros de instancia pertenecen a objetos (instancias de clases).

En la lista siguiente se proporciona una visión general de los tipos de miembros que puede contener una clase.

- **Constantes**: Valores constantes asociados a la clase
- **Campos**:  variables que están asociadas a la clase
- **Métodos**:  acciones que puede realizar la clase.
- **Propiedades**: Acciones asociadas a la lectura y escritura de propiedades con nombre de la clase
- **Indizadores**: Acciones asociadas a la indexación de instancias de la clase como una matriz
- **Eventos**: Notificaciones que puede generar la clase
- **Operadores**: Conversiones y operadores de expresión admitidos por la clase
- **Constructores**: Acciones necesarias para inicializar instancias de la clase o la clase propiamente dicha
- **Finalizadores**: acciones que deben realizarse antes de que las instancias de la clase se descarten de forma permanente
- **Tipos**: Tipos anidados declarados por la clase

## <a name="accessibility"></a>Accesibilidad

Cada miembro de una clase tiene asociada una accesibilidad, que controla las regiones del texto del programa que pueden acceder al miembro. Existen seis formas de accesibilidad posibles. A continuación se resumen los modificadores de acceso.

- `public`: El acceso no está limitado.
- `private`: El acceso está limitado a esta clase.
- `protected`: El acceso está limitado a esta clase o a las clases derivadas de esta clase.
- `internal`: El acceso está limitado al ensamblado actual (`.exe` o `.dll`).
- `protected internal`: El acceso está limitado a esta clase, las clases derivadas de la misma o las clases que forman parte del mismo ensamblado.
- `private protected`: El acceso está limitado a esta clase o a las clases derivadas de este tipo que forman parte del mismo ensamblado.

## <a name="fields"></a>Campos

Un *campo* es una variable que está asociada con una clase o a una instancia de una clase.

Un campo declarado con el modificador "static" define un campo estático. Un campo estático identifica exactamente una ubicación de almacenamiento. Independientemente del número de instancias de una clase que se creen, solo hay una única copia de un campo estático.

Un campo declarado sin el modificador "static" define un campo de instancia. Cada instancia de una clase contiene una copia independiente de todos los campos de instancia de esa clase.

En el ejemplo siguiente, cada instancia de la clase `Color` tiene una copia independiente de los campos de instancia `r`, `g` y `b`, pero solo hay una copia de los campos estáticos `Black`, `White`, `Red`, `Green` y `Blue`:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ColorClassDefinition":::

Como se muestra en el ejemplo anterior, los *campos de solo lectura* se puede declarar con un modificador `readonly`. La asignación a un campo de solo lectura únicamente se puede producir como parte de la declaración del campo o en un constructor de la misma clase.

## <a name="methods"></a>Métodos

Un *método* es un miembro que implementa un cálculo o una acción que puede realizar un objeto o una clase. A los *métodos estáticos* se accede a través de la clase. A los *métodos de instancia* se accede a través de instancias de la clase.

Los métodos pueden tener una lista de *parámetros*, los cuales representan valores o referencias a variables que se pasan al método. Los métodos tienen un *tipo de valor devuelto*, el cual especifica el tipo del valor calculado y devuelto por el método. El tipo de valor devuelto de un método es `void` si no devuelve un valor.

Al igual que los tipos, los métodos también pueden tener un conjunto de parámetros de tipo, para lo cuales se deben especificar argumentos de tipo cuando se llama al método. A diferencia de los tipos, los argumentos de tipo a menudo se pueden deducir de los argumentos de una llamada al método y no es necesario proporcionarlos explícitamente.

La *signatura* de un método debe ser única en la clase en la que se declara el método. La signatura de un método se compone del nombre del método, el número de parámetros de tipo y el número, los modificadores y los tipos de sus parámetros. La signatura de un método no incluye el tipo de valor devuelto.

Cuando el cuerpo del método es una expresión única, el método se puede definir con un formato de expresión compacta, tal y como se muestra en el ejemplo siguiente:

```csharp
public override ToString() => "This is an object";
```

### <a name="parameters"></a>Parámetros

Los parámetros se usan para pasar valores o referencias a variables a métodos. Los parámetros de un método obtienen sus valores reales de los *argumentos* que se especifican cuando se invoca el método. Hay cuatro tipos de parámetros: parámetros de valor, parámetros de referencia, parámetros de salida y matrices de parámetros.

Un *parámetro de valor* se usa para pasar argumentos de entrada. Un parámetro de valor corresponde a una variable local que obtiene su valor inicial del argumento que se ha pasado para el parámetro. Las modificaciones de un parámetro de valor no afectan el argumento que se ha pasado para el parámetro.

Los parámetros de valor pueden ser opcionales; se especifica un valor predeterminado para que se puedan omitir los argumentos correspondientes.

Un *parámetro de referencia* se usa para pasar argumentos mediante una referencia. El argumento pasado para un parámetro de referencia debe ser una variable con un valor definido. Durante la ejecución del método, el parámetro de referencia representa la misma ubicación de almacenamiento que la variable del argumento. Un parámetro de referencia se declara con el modificador `ref`. En el ejemplo siguiente se muestra el uso de parámetros `ref`.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="RefExample":::

Un *parámetro de salida* se usa para pasar argumentos mediante una referencia. Es similar a un parámetro de referencia, excepto que no necesita que asigne un valor explícitamente al argumento proporcionado por el autor de la llamada. Un parámetro de salida se declara con el modificador `out`. En el siguiente ejemplo se muestra el uso de los parámetros `out` con la sintaxis que se ha presentado en C# 7.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="OutExample":::

Una *matriz de parámetros* permite que se pasen a un método un número variable de argumentos. Una matriz de parámetros se declara con el modificador `params`. Solo el último parámetro de un método puede ser una matriz de parámetros y el tipo de una matriz de parámetros debe ser un tipo de matriz unidimensional. Los métodos `Write` y `WriteLine` de la clase <xref:System.Console?displayProperty=nameWithType> son buenos ejemplos de uso de la matriz de parámetros. Se declaran de la manera siguiente.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ConsoleExtract":::

Dentro de un método que usa una matriz de parámetros, la matriz de parámetros se comporta exactamente igual que un parámetro normal de un tipo de matriz. Pero en una invocación de un método con una matriz de parámetros, es posible pasar un único argumento del tipo de matriz de parámetros o cualquier número de argumentos del tipo de elemento de la matriz de parámetros. En este caso, una instancia de matriz se e inicializa automáticamente con los argumentos dados. Este ejemplo

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UseParamsArgs":::

es equivalente a escribir lo siguiente.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="CompilerParams":::

### <a name="method-body-and-local-variables"></a>Cuerpo del método y variables locales

El cuerpo de un método especifica las instrucciones que se ejecutarán cuando se invoca el método.

Un cuerpo del método puede declarar variables que son específicas de la invocación del método. Estas variables se denominan *variables locales*. Una declaración de variable local especifica un nombre de tipo, un nombre de variable y, posiblemente, un valor inicial. En el ejemplo siguiente se declara una variable local `i` con un valor inicial de cero y una variable local `j` sin ningún valor inicial.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="SquaresClass":::

C# requiere que se *asigne definitivamente* una variable local antes de que se pueda obtener su valor. Por ejemplo, si la declaración de `i` anterior no incluyera un valor inicial, el compilador notificaría un error con los usos posteriores de `i` porque `i` no se asignaría definitivamente en esos puntos del programa.

Puede usar una instrucción `return` para devolver el control a su llamador. En un método que devuelve `void`, las instrucciones `return` no pueden especificar una expresión. En un método que devuelve valores distintos de void, las instrucciones `return` deben incluir una expresión que calcula el valor devuelto.

### <a name="static-and-instance-methods"></a>Métodos estáticos y de instancia

Un método declarado con un modificador `static` es un *método estático*. Un método estático no opera en una instancia específica y solo puede acceder directamente a miembros estáticos.

Un método declarado sin un modificador `static` es un *método de instancia*. Un método de instancia opera en una instancia específica y puede acceder a miembros estáticos y de instancia. Se puede acceder explícitamente a la instancia en la que se invoca un método de instancia como `this`. Es un error hacer referencia a `this` en un método estático.

La siguiente clase `Entity` tiene miembros estáticos y de instancia.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="EntityClass":::

Cada instancia de `Entity` contiene un número de serie (y, probablemente, otra información que no se muestra aquí). El constructor `Entity` (que es como un método de instancia) inicializa la nueva instancia con el siguiente número de serie disponible. Como el constructor es un miembro de instancia, se le permite acceder al campo de instancia `_serialNo` y al campo estático `s_nextSerialNo`.

Los métodos estáticos `GetNextSerialNo` y `SetNextSerialNo` pueden acceder al campo estático `s_nextSerialNo`, pero sería un error para ellas acceder directamente al campo de instancia `_serialNo`.

En el ejemplo siguiente se muestra el uso de la clase `Entity`.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UsingEntity":::

Los métodos estáticos `SetNextSerialNo` y `GetNextSerialNo` se invocan en la clase, mientras que el método de instancia `GetSerialNo` se invoca en instancias de la clase.

### <a name="virtual-override-and-abstract-methods"></a>Métodos virtual, de reemplazo y abstracto

Cuando una declaración de método de instancia incluye un modificador `virtual`, se dice que el método es un *método virtual*. Cuando no existe un modificador virtual, se dice que el método es un *método no virtual*.

Cuando se invoca un método virtual, el *tipo en tiempo de ejecución* de la instancia para la que tiene lugar esa invocación determina la implementación del método real que se invocará. En una invocación de método no virtual, el *tipo en tiempo de compilación* de la instancia es el factor determinante.

Un método virtual puede ser *reemplazado* en una clase derivada. Cuando una declaración de método de instancia incluye un modificador "override", el método reemplaza un método virtual heredado con la misma signatura. Una declaración de método virtual presenta un nuevo método. Una declaración de método de reemplazo especializa un método virtual heredado existente proporcionando una nueva implementación de ese método.

Un *método abstracto* es un método virtual sin implementación. Un método abstracto se declara con el modificador `abstract` y solo se permite en una clase abstracta. Un método abstracto debe reemplazarse en todas las clases derivadas no abstractas.

En el ejemplo siguiente se declara una clase abstracta, `Expression`, que representa un nodo de árbol de expresión y tres clases derivadas, `Constant`, `VariableReference` y `Operation`, que implementan nodos de árbol de expresión para constantes, referencias a variables y operaciones aritméticas. Este ejemplo es similar a los tipos de árbol de expresión, pero no está relacionada con ellos.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="WorkingWithExpressions":::

Las cuatro clases anteriores se pueden usar para modelar expresiones aritméticas. Por ejemplo, usando instancias de estas clases, la expresión `x + 3` se puede representar de la manera siguiente.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UseExpressions":::

El método `Evaluate` de una instancia `Expression` se invoca para evaluar la expresión determinada y generar un valor `double`. El método toma un argumento `Dictionary` que contiene nombres de variables (como claves de las entradas) y valores (como valores de las entradas). Como `Evaluate` es un método abstracto, las clases no abstractas que derivan de `Expression` deben invalidar `Evaluate`.

Una implementación de `Constant` de `Evaluate` simplemente devuelve la constante almacenada. Una implementación de `VariableReference` busca el nombre de variable en el diccionario y devuelve el valor resultante. Una implementación de `Operation` evalúa primero los operandos izquierdo y derecho (mediante la invocación recursiva de sus métodos `Evaluate`) y luego realiza la operación aritmética correspondiente.

El siguiente programa usa las clases `Expression` para evaluar la expresión `x * (y + 2)` para los distintos valores de `x` y `y`.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UsingExpressions":::

### <a name="method-overloading"></a>Sobrecarga de métodos

La *sobrecarga* de métodos permite que varios métodos de la misma clase tengan el mismo nombre mientras tengan signaturas únicas. Al compilar una invocación de un método sobrecargado, el compilador usa la *resolución de sobrecarga* para determinar el método concreto que de invocará. La resolución de sobrecarga busca el método que mejor coincida con los argumentos. Si no se puede encontrar la mejor coincidencia, se genera un error. En el ejemplo siguiente se muestra la resolución de sobrecarga en vigor. El comentario para cada invocación del método `UsageExample` muestra qué método se invoca.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="Overloading":::

Tal como se muestra en el ejemplo, un método determinado siempre se puede seleccionar mediante la conversión explícita de los argumentos en los tipos de parámetros exactos o los argumentos de tipo.

## <a name="other-function-members"></a>Otros miembros de función

Los miembros que contienen código ejecutable se conocen colectivamente como *miembros de función* de una clase. En la sección anterior se describen los métodos, que son los tipos principales de los miembros de función. En esta sección se describen los otros tipos de miembros de función admitidos por C#: constructores, propiedades, indexadores, eventos, operadores y finalizadores.

En el ejemplo siguiente se muestra una clase genérica llamada `MyList<T>`, que implementa una lista creciente de objetos. La clase contiene varios ejemplos de los tipos más comunes de miembros de función.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListExample":::

### <a name="constructors"></a>Constructores

C# admite constructores de instancia y estáticos. Un *constructor de instancia* es un miembro que implementa las acciones necesarias para inicializar una instancia de una clase. Un *constructor estático* es un miembro que implementa las acciones necesarias para inicializar una clase en sí misma cuando se carga por primera vez.

Un constructor se declara como un método sin ningún tipo de valor devuelto y el mismo nombre que la clase contenedora. Si una declaración de constructor incluye un modificador `static`, declara un constructor estático. De lo contrario, declara un constructor de instancia.

Los constructores de instancia pueden sobrecargarse y tener parámetros opcionales. Por ejemplo, la clase `MyList<T>` declara un constructor de instancia con único parámetro `int` opcional. Los constructores de instancia se invocan mediante el operador `new`. Las siguientes instrucciones asignan dos instancias `MyList<string>` mediante el constructor de la clase `MyList` con y sin el argumento opcional.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="CreateLists":::

A diferencia de otros miembros, los constructores de instancias no se heredan. Una clase no tiene constructores de instancia que no sean los que se declaren realmente en la misma. Si no se proporciona ningún constructor de instancia para una clase, se proporciona automáticamente uno vacío sin ningún parámetro.

### <a name="properties"></a>Propiedades

Las *propiedades* son una extensión natural de los campos. Ambos son miembros con nombre con tipos asociados y la sintaxis para acceder a los campos y las propiedades es la misma. Pero a diferencia de los campos, las propiedades no denotan ubicaciones de almacenamiento. Las propiedades tienen *descriptores de acceso* que especifican las instrucciones ejecutadas cuando se leen o escriben sus valores.

Una propiedad se declara como un campo, salvo que la declaración finaliza con un descriptor de acceso get o un descriptor de acceso set escrito entre los delimitadores `{` y `}` en lugar de finalizar en un punto y coma. Una propiedad que tiene un descriptor de acceso get y un descriptor de acceso set es una *propiedad de lectura y escritura*, una propiedad que tiene solo un descriptor de acceso get es una *propiedad de solo lectura* y una propiedad que tiene solo un descriptor de acceso set es una *propiedad de solo escritura*.

Un descriptor de acceso get corresponde a un método sin parámetros con un valor devuelto del tipo de propiedad. Un descriptor de acceso set corresponde a un método con un solo parámetro denominado value y ningún tipo de valor devuelto. El descriptor de acceso get calcula el valor de la propiedad. El descriptor de acceso set proporciona un nuevo valor para la propiedad. Cuando la propiedad es el destino de una asignación, o el operando de `++` o `--`, se invoca al descriptor de acceso set. En otros casos en los que se hace referencia a la propiedad, se invoca al descriptor de acceso get.

 Cuando se hace referencia a una propiedad como el destino de una asignación o como el operando de ++ o--, el descriptor de acceso set se invoca con un argumento que proporciona el nuevo valor.

La clase `MyList<T>` declara dos propiedades, `Count` y `Capacity`, que son de solo lectura y de lectura y escritura, respectivamente. El código siguiente es un ejemplo de uso de estas propiedades:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="AccessProperties":::

De forma similar a los campos y métodos, C# admite propiedades de instancia y propiedades estáticas. Las propiedades estáticas se declaran con el modificador "static", y las propiedades de instancia se declaran sin él.

Los descriptores de acceso de una propiedad pueden ser virtuales. Cuando una declaración de propiedad incluye un modificador `virtual`, `abstract` o `override`, se aplica a los descriptores de acceso de la propiedad.

### <a name="indexers"></a>Indexadores

Un *indexador* es un miembro que permite indexar de la misma manera que una matriz. Un indexador se declara como una propiedad, excepto por el hecho que el nombre del miembro es `this`, seguido por una lista de parámetros que se escriben entre los delimitadores `[` y `]`. Los parámetros están disponibles en los descriptores de acceso del indexador. De forma similar a las propiedades, los indexadores pueden ser lectura y escritura, de solo lectura y de solo escritura, y los descriptores de acceso de un indexador pueden ser virtuales.

La clase `MyList<T>` declara un único indexador de lectura y escritura que toma un parámetro `int`. El indexador permite indexar instancias de `MyList<T>` con valores `int`. Por ejemplo:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListAccess":::

Los indizadores se pueden sobrecargar. Una clase puede declarar varios indexadores siempre y cuando el número o los tipos de sus parámetros sean diferentes.

### <a name="events"></a>Eventos

Un *evento* es un miembro que permite que una clase u objeto proporcionen notificaciones. Un evento se declara como un campo, excepto por el hecho de que la declaración incluye una palabra clave `event`, y el tipo debe ser un tipo delegado.

Dentro de una clase que declara un miembro de evento, el evento se comporta como un campo de un tipo delegado (siempre que el evento no sea abstracto y no declare descriptores de acceso). El campo almacena una referencia a un delegado que representa los controladores de eventos que se han agregado al evento. Si no existen controladores de eventos, el campo es `null`.

La clase `MyList<T>` declara un único miembro de evento llamado `Changed`, lo que indica que se ha agregado un nuevo elemento a la lista. El método virtual `OnChanged` genera el evento cambiado, y comprueba primero si el evento es `null` (lo que significa que no existen controladores). La noción de generar un evento es equivalente exactamente a invocar el delegado representado por el evento. No hay ninguna construcción especial de lenguaje para generar eventos.

Los clientes reaccionan a los eventos mediante *controladores de eventos*. Los controladores de eventos se asocian mediante el operador `+=` y se quitan con el operador `-=`. En el ejemplo siguiente se asocia un controlador de eventos con el evento `Changed` de un objeto `MyList<string>`.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="RespondToEvents":::

Para escenarios avanzados donde se quiere controlar el almacenamiento subyacente de un evento, una declaración de evento puede proporcionar de forma explícita los descriptores de acceso `add` y `remove`, que son similares al descriptor de acceso `set` de una propiedad.

### <a name="operators"></a>Operadores

Un *operador* es un miembro que define el significado de aplicar un operador de expresión determinado a las instancias de una clase. Se pueden definir tres tipos de operadores: operadores unarios, operadores binarios y operadores de conversión. Todos los operadores se deben declarar como `public` y `static`.

La clase `MyList<T>` declara dos operadores, `operator ==` y `operator !=`. Los operadores de reemplazo proporcionan un nuevo significado a expresiones que aplican esos operadores a instancias `MyList`. En concreto, los operadores definen la igualdad de dos instancias `MyList<T>` como la comparación de cada uno de los objetos contenidos con sus métodos `Equals`. En el ejemplo siguiente se usa el operador `==` para comparar dos instancias `MyList<int>`.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListAddition":::

El primer objeto `Console.WriteLine` genera `True` porque las dos listas contienen el mismo número de objetos con los mismos valores en el mismo orden. Si `MyList<T>` no hubiera definido `operator ==`, el primer objeto `Console.WriteLine` habría generado `False` porque `a` y `b` hacen referencia a diferentes instancias de `MyList<int>`.

### <a name="finalizers"></a>Finalizadores

Un *finalizador* es un miembro que implementa las acciones necesarias para finalizar una instancia de una clase. Normalmente, se necesita un finalizador para liberar los recursos no administrados. Los finalizadores no pueden tener parámetros, no pueden tener modificadores de accesibilidad y no se pueden invocar de forma explícita. El finalizador de una instancia se invoca automáticamente durante la recolección de elementos no utilizados. Para obtener más información, consulte el artículo sobre los [finalizadores](../programming-guide/classes-and-structs/destructors.md).

El recolector de elementos no utilizados tiene una amplia libertad para decidir cuándo debe recolectar objetos y ejecutar finalizadores. En concreto, los intervalos de las invocaciones de finalizador no son deterministas y los finalizadores se pueden ejecutar en cualquier subproceso. Por estas y otras razones, las clases deben implementar finalizadores solo cuando no haya otras soluciones que sean factibles.

La instrucción `using` proporciona un mejor enfoque para la destrucción de objetos.

## <a name="expressions"></a>Expresiones

Las *expresiones* se construyen con *operandos* y *operadores*. Los operadores de una expresión indican qué operaciones se aplican a los operandos. Ejemplos de operadores incluyen `+`, `-`, `*`, `/` y `new`. Algunos ejemplos de operandos son literales, campos, variables locales y expresiones.

Cuando una expresión contiene varios operadores, su *precedencia* controla el orden en el que se evalúan los operadores individuales. Por ejemplo, la expresión `x + y * z` se evalúa como `x + (y * z)` porque el operador `*` tiene mayor precedencia que el operador `+`.

Cuando un operando se encuentra entre dos operadores con la misma precedencia, la *asociatividad* de los operadores controla el orden en que se realizan las operaciones:

* Excepto los operadores de asignación y los operadores de fusión de NULL, todos los operadores binarios son *asociativos a la izquierda*, lo que significa que las operaciones se realizan de izquierda a derecha. Por ejemplo, `x + y + z` se evalúa como `(x + y) + z`.
* Los operadores de asignación, los operadores de fusión de NULL `??` y `??=` y el operador condicional `?:` son *asociativos a la derecha*, lo que significa que las operaciones se realizan de derecha a izquierda. Por ejemplo, `x = y = z` se evalúa como `x = (y = z)`.

La precedencia y la asociatividad pueden controlarse mediante paréntesis. Por ejemplo, `x + y * z` primero multiplica `y` por `z` y luego suma el resultado a `x`, pero `(x + y) * z` primero suma `x` y `y` y luego multiplica el resultado por `z`.

La mayoría de los operadores se pueden [*sobrecargar*](../language-reference/operators/operator-overloading.md). La sobrecarga de operador permite la especificación de implementaciones de operadores definidas por el usuario para operaciones donde uno o ambos operandos son de un tipo de struct o una clase definidos por el usuario.

C# ofrece una serie de operadores para realizar operaciones [aritméticas](../language-reference/operators/arithmetic-operators.md), [lógicas](../language-reference/operators/boolean-logical-operators.md), [de desplazamiento y bit a bit](../language-reference/operators/bitwise-and-shift-operators.md), además de comparaciones de [igualdad](../language-reference/operators/equality-operators.md) y de [orden](../language-reference/operators/comparison-operators.md).

Para obtener la lista completa de los operadores de C# ordenados por nivel de prioridad, vea [Operadores de C#](../language-reference/operators/index.md).

## <a name="statements"></a>Instrucciones

Las acciones de un programa se expresan mediante *instrucciones*. C# admite varios tipos de instrucciones diferentes, varias de las cuales se definen en términos de instrucciones insertadas.

- Un *bloque* permite que se escriban varias instrucciones en contextos donde se permite una única instrucción. Un bloque se compone de una lista de instrucciones escritas entre los delimitadores `{` y `}`.
- Las *instrucciones de declaración* se usan para declarar variables locales y constantes.
- Las *instrucciones de expresión* se usan para evaluar expresiones. Las expresiones que pueden usarse como instrucciones incluyen invocaciones de método, asignaciones de objetos mediante el operador `new`, asignaciones mediante `=` y los operadores de asignación compuestos, operaciones de incremento y decremento mediante los operadores `++` y `--` y expresiones `await`.
- Las *instrucciones de selección* se usan para seleccionar una de varias instrucciones posibles para su ejecución en función del valor de alguna expresión. Este grupo contiene las instrucciones `if` y `switch`.
- Las *instrucciones de iteración* se usan para ejecutar una instrucción insertada de forma repetida. Este grupo contiene las instrucciones `while`, `do`, `for` y `foreach`.
- Las *instrucciones de salto* se usan para transferir el control. Este grupo contiene las instrucciones `break`, `continue`, `goto`, `throw`, `return` y `yield`.
- La instrucción `try`... `catch` se usa para detectar excepciones que se producen durante la ejecución de un bloque, y la instrucción `try`... `finally` se usa para especificar el código de finalización que siempre se ejecuta, tanto si se ha producido una excepción como si no.
- Las instrucciones `checked` y `unchecked` sirven para controlar el contexto de comprobación de desbordamiento para conversiones y operaciones aritméticas de tipo integral.
- La instrucción `lock` se usa para obtener el bloqueo de exclusión mutua para un objeto determinado, ejecutar una instrucción y, luego, liberar el bloqueo.
- La instrucción `using` se usa para obtener un recurso, ejecutar una instrucción y, luego, eliminar dicho recurso.

A continuación se enumeran los tipos de instrucciones que se pueden usar:

* Declaración de variable local
* Declaración de constante local
* Instrucción de expresión
* Instrucción `if`
* Instrucción `switch`
* Instrucción `while`
* Instrucción `do`
* Instrucción `for`
* Instrucción `foreach`
* Instrucción `break`
* Instrucción `continue`
* Instrucción `goto`
* Instrucción `return`
* Instrucción `yield`
* Instrucciones `throw` y `try`
* Instrucciones `checked` y `unchecked`
* Instrucción `lock`
* Instrucción `using`

>[!div class="step-by-step"]
>[Anterior](types.md)
>[Siguiente](features.md)
