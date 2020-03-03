---
title: 'Clases y objetos en C#: un paseo por el lenguaje C#'
description: ¿Nuevo en C#? Lea esta información general sobre clases, objetos y herencia
ms.date: 02/27/2020
ms.assetid: 63a89bde-0f05-4bc4-b0cd-4f693854f0cd
ms.openlocfilehash: c178e11b5667905f75538555c8a309e2fdb4a9ef
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159187"
---
# <a name="classes-and-objects"></a>Clases y objetos

Las *clases* son los tipos más fundamentales de C#. Una clase es una estructura de datos que combina estados (campos) y acciones (métodos y otros miembros de función) en una sola unidad. Una clase proporciona una definición para *instancias* creadas dinámicamente de la clase, también conocidas como *objetos*. Las clases admiten *herencia* y *polimorfismo*, mecanismos por los que las *clases derivadas* pueden extender y especializar *clases base*.

Las clases nuevas se crean mediante declaraciones de clase. Una declaración de clase se inicia con un encabezado que especifica los atributos y modificadores de la clase, el nombre de la clase, la clase base (si se indica) y las interfaces implementadas por la clase. Al encabezado le sigue el cuerpo de la clase, que consta de una lista de declaraciones de miembros escritas entre los delimitadores `{` y `}`.

En el código siguiente se muestra una declaración de una clase simple denominada `Point`:

[!code-csharp[PointClass](~/samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L11)]

Las instancias de clases se crean mediante el operador `new`, que asigna memoria para una nueva instancia, invoca un constructor para inicializar la instancia y devuelve una referencia a la instancia. Las instrucciones siguientes crean dos objetos Point y almacenan las referencias en esos objetos en dos variables:

[!code-csharp[PointExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L9-L10)]

La memoria ocupada por un objeto se reclama automáticamente cuando el objeto ya no es accesible. En C#, no es necesario ni posible desasignar objetos de forma explícita.

## <a name="members"></a>Miembros

Los miembros de una clase son miembros estáticos o miembros de instancia. Los miembros estáticos pertenecen a clases y los miembros de instancia pertenecen a objetos (instancias de clases).

En la lista siguiente se proporciona una visión general de los tipos de miembros que puede contener una clase.

- Constantes
  - Valores constantes asociados a la clase
- Campos
  - Variables de la clase
- Métodos
  - Cálculos y acciones que pueden realizarse mediante la clase
- Propiedades
  - Acciones asociadas a la lectura y escritura de propiedades con nombre de la clase
- Indizadores
  - Acciones asociadas a la indexación de instancias de la clase como una matriz
- Eventos
  - Notificaciones que puede generar la clase
- Operadores
  - Conversiones y operadores de expresión admitidos por la clase
- Constructores
  - Acciones necesarias para inicializar instancias de la clase o la clase propiamente dicha
- Finalizadores
  - Acciones que deben realizarse antes de que las instancias de la clase se descarten de forma permanente
- Tipos
  - Tipos anidados declarados por la clase

## <a name="accessibility"></a>Accesibilidad

Cada miembro de una clase tiene asociada una accesibilidad, que controla las regiones del texto del programa que pueden acceder al miembro. Existen seis formas de accesibilidad posibles. A continuación se resumen los modificadores de acceso.

- `public`
  - El acceso no está limitado.
- `protected`
  - El acceso está limitado a esta clase o a las clases derivadas de esta clase.
- `internal`
  - El acceso está limitado al ensamblado actual (.exe, .dll, etc.).
- `protected internal`
  - El acceso está limitado a la clase contenedora, las clases derivadas de la clase contenedora, o bien las clases dentro del mismo ensamblado.
- `private`
  - El acceso está limitado a esta clase.
- `private protected`
  - El acceso está limitado a la clase contenedora o las clases derivadas del tipo contenedor dentro del mismo ensamblado.

## <a name="type-parameters"></a>Parámetros de tipo

Una definición de clase puede especificar un conjunto de parámetros de tipo poniendo tras el nombre de clase una lista de nombres de parámetro de tipo entre corchetes angulares. Los parámetros de tipo pueden usarse luego en el cuerpo de las declaraciones de clase para definir a los miembros de la clase. En el ejemplo siguiente, los parámetros de tipo de `Pair` son `TFirst` y `TSecond`:

[!code-csharp[Pair](~/samples/snippets/csharp/tour/classes-and-objects/Pair.cs#L3-L7)]

Un tipo de clase que se declara para tomar parámetros de tipo se conoce como *tipo de clase genérica*. Los tipos de estructura, interfaz y delegado también pueden ser genéricos.
Cuando se usa la clase genérica, se deben proporcionar argumentos de tipo para cada uno de los parámetros de tipo:

[!code-csharp[PairExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L15-L17)]

Un tipo genérico con argumentos de tipo proporcionado, como `Pair<int,string>` anteriormente, se conoce como *tipo construido*.

## <a name="base-classes"></a>Clases base

Una declaración de clase puede especificar una clase base colocando después del nombre de clase y los parámetros de tipo dos puntos seguidos del nombre de la clase base. Omitir una especificación de la clase base es igual que derivarla del tipo `object`. En el ejemplo siguiente, la clase base de `Point3D` es `Point` y la clase base de `Point` es `object`:

[!code-csharp[Point3DClass](~/samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L20)]

Una clase hereda a los miembros de su clase base. La herencia significa que una clase contiene implícitamente todos los miembros de su clase base, excepto la instancia y los constructores estáticos, y los finalizadores de la clase base. Una clase derivada puede agregar nuevos miembros a aquellos de los que hereda, pero no puede quitar la definición de un miembro heredado. En el ejemplo anterior, `Point3D` hereda los campos `x` y `y` de `Point` y cada instancia de `Point3D` contiene tres campos: `x`, `y` y `z`.

Existe una conversión implícita de un tipo de clase a cualquiera de sus tipos de clase base. Una variable de un tipo de clase puede hacer referencia a una instancia de esa clase o a una instancia de cualquier clase derivada. Por ejemplo, dadas las declaraciones de clase anteriores, una variable de tipo `Point` puede hacer referencia a una instancia de `Point` o `Point3D`:

[!code-csharp[Point3DExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L22-L23)]

## <a name="fields"></a>Campos

Un *campo* es una variable que está asociada con una clase o a una instancia de una clase.

Un campo declarado con el modificador "static" define un campo estático. Un campo estático identifica exactamente una ubicación de almacenamiento. Independientemente del número de instancias de una clase que se creen, solo hay una única copia de un campo estático.

Un campo declarado sin el modificador "static" define un campo de instancia. Cada instancia de una clase contiene una copia independiente de todos los campos de instancia de esa clase.

En el ejemplo siguiente, cada instancia de la clase `Color` tiene una copia independiente de los campos de instancia `r`, `g` y `b`, pero solo hay una copia de los campos estáticos `Black`, `White`, `Red`, `Green` y `Blue`:

[!code-csharp[ColorClass](~/samples/snippets/csharp/tour/classes-and-objects/Color.cs#L3-L17)]

Como se muestra en el ejemplo anterior, los *campos de solo lectura* se puede declarar con un modificador `readonly`. La asignación a un campo `readonly` solo se puede producir como parte de la declaración del campo o en un constructor de la misma clase.

## <a name="methods"></a>Métodos

Un *método* es un miembro que implementa un cálculo o una acción que puede realizar un objeto o una clase. A los *métodos estáticos* se accede a través de la clase. A los *métodos de instancia* se accede a través de instancias de la clase.

Los métodos pueden tener una lista de *parámetros*, que representan valores o referencias a variables que se pasan al método, y un *tipo de valor devuelto*, que especifica el tipo del valor calculado y devuelto por el método. El tipo de valor devuelto de un método es `void` si no devuelve un valor.

Al igual que los tipos, los métodos también pueden tener un conjunto de parámetros de tipo, para lo cuales se deben especificar argumentos de tipo cuando se llama al método. A diferencia de los tipos, los argumentos de tipo a menudo se pueden deducir de los argumentos de una llamada al método y no es necesario proporcionarlos explícitamente.

La *signatura* de un método debe ser única en la clase en la que se declara el método. La signatura de un método se compone del nombre del método, el número de parámetros de tipo y el número, los modificadores y los tipos de sus parámetros. La signatura de un método no incluye el tipo de valor devuelto.

### <a name="parameters"></a>Parámetros

Los parámetros se usan para pasar valores o referencias a variables a métodos. Los parámetros de un método obtienen sus valores reales de los *argumentos* que se especifican cuando se invoca el método. Hay cuatro tipos de parámetros: parámetros de valor, parámetros de referencia, parámetros de salida y matrices de parámetros.

Un *parámetro de valor* se usa para pasar argumentos de entrada. Un parámetro de valor corresponde a una variable local que obtiene su valor inicial del argumento que se ha pasado para el parámetro. Las modificaciones de un parámetro de valor no afectan el argumento que se ha pasado para el parámetro.

Los parámetros de valor pueden ser opcionales; se especifica un valor predeterminado para que se puedan omitir los argumentos correspondientes.

Un *parámetro de referencia* se usa para pasar argumentos mediante una referencia. El argumento pasado para un parámetro de referencia debe ser una variable con un valor definitivo, y durante la ejecución del método, el parámetro de referencia representa la misma ubicación de almacenamiento que la variable del argumento. Un parámetro de referencia se declara con el modificador `ref`. En el ejemplo siguiente se muestra el uso de parámetros `ref`.

[!code-csharp[swapExample](~/samples/snippets/csharp/tour/classes-and-objects/RefExample.cs#L3-L18)]

Un *parámetro de salida* se usa para pasar argumentos mediante una referencia. Es similar a un parámetro de referencia, excepto que no necesita que asigne un valor explícitamente al argumento proporcionado por el autor de la llamada. Un parámetro de salida se declara con el modificador `out`. En el siguiente ejemplo se muestra el uso de los parámetros `out` con la sintaxis que se ha presentado en C# 7.

[!code-csharp[OutExample](~/samples/snippets/csharp/tour/classes-and-objects/OutExample.cs#L3-L17)]

Una *matriz de parámetros* permite que se pasen a un método un número variable de argumentos. Una matriz de parámetros se declara con el modificador `params`. Solo el último parámetro de un método puede ser una matriz de parámetros y el tipo de una matriz de parámetros debe ser un tipo de matriz unidimensional. Los métodos Write y WriteLine de la clase <xref:System.Console?displayProperty=nameWithType> son buenos ejemplos de uso de la matriz de parámetros. Se declaran de la manera siguiente.

[!code-csharp[ConsoleExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L78-L83)]

Dentro de un método que usa una matriz de parámetros, la matriz de parámetros se comporta exactamente igual que un parámetro normal de un tipo de matriz. Pero en una invocación de un método con una matriz de parámetros, es posible pasar un único argumento del tipo de matriz de parámetros o cualquier número de argumentos del tipo de elemento de la matriz de parámetros. En este caso, una instancia de matriz se e inicializa automáticamente con los argumentos dados. Este ejemplo

[!code-csharp[StringFormat](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L55-L55)]

es equivalente a escribir lo siguiente.

[!code-csharp[StringFormat2](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L30-L35)]

### <a name="method-body-and-local-variables"></a>Cuerpo del método y variables locales

El cuerpo de un método especifica las instrucciones que se ejecutarán cuando se invoca el método.

Un cuerpo del método puede declarar variables que son específicas de la invocación del método. Estas variables se denominan *variables locales*. Una declaración de variable local especifica un nombre de tipo, un nombre de variable y, posiblemente, un valor inicial. En el ejemplo siguiente se declara una variable local `i` con un valor inicial de cero y una variable local `j` sin ningún valor inicial.

[!code-csharp[Squares](~/samples/snippets/csharp/tour/classes-and-objects/Squares.cs#L3-L17)]

C# requiere que se *asigne definitivamente* una variable local antes de que se pueda obtener su valor. Por ejemplo, si la declaración de `i` anterior no incluyera un valor inicial, el compilador notificaría un error con los usos posteriores de `i` porque `i` no se asignaría definitivamente en esos puntos del programa.

Puede usar una instrucción `return` para devolver el control a su llamador. En un método que devuelve `void`, las instrucciones `return` no pueden especificar una expresión. En un método que devuelve valores distintos de void, las instrucciones `return` deben incluir una expresión que calcula el valor devuelto.

### <a name="static-and-instance-methods"></a>Métodos estáticos y de instancia

Un método declarado con un modificador static es un *método estático*. Un método estático no opera en una instancia específica y solo puede acceder directamente a miembros estáticos.

Un método declarado sin un modificador static es un *método de instancia*. Un método de instancia opera en una instancia específica y puede acceder a miembros estáticos y de instancia. Se puede acceder explícitamente a la instancia en la que se invoca un método de instancia como `this`. Es un error hacer referencia a `this` en un método estático.

La siguiente clase `Entity` tiene miembros estáticos y de instancia.

[!code-csharp[Entity](~/samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L16-L36)]

Cada instancia de `Entity` contiene un número de serie (y, probablemente, otra información que no se muestra aquí). El constructor `Entity` (que es como un método de instancia) inicializa la nueva instancia con el siguiente número de serie disponible. Como el constructor es un miembro de instancia, se le permite acceder al campo de instancia `serialNo` y al campo estático `nextSerialNo`.

Los métodos estáticos `GetNextSerialNo` y `SetNextSerialNo` pueden acceder al campo estático `nextSerialNo`, pero sería un error para ellas acceder directamente al campo de instancia `serialNo`.

En el ejemplo siguiente se muestra el uso de la clase Entity.

[!code-csharp[EntityExample](~/samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L3-L15)]

Los métodos estáticos `SetNextSerialNo` y `GetNextSerialNo` se invocan en la clase, mientras que el método de instancia `GetSerialNo` se invoca en instancias de la clase.

### <a name="virtual-override-and-abstract-methods"></a>Métodos virtual, de reemplazo y abstracto

Cuando una declaración de método de instancia incluye un modificador `virtual`, se dice que el método es un *método virtual*. Cuando no existe un modificador virtual, se dice que el método es un *método no virtual*.

Cuando se invoca un método virtual, el *tipo en tiempo de ejecución* de la instancia para la que tiene lugar esa invocación determina la implementación del método real que se invocará. En una invocación de método no virtual, el *tipo en tiempo de compilación* de la instancia es el factor determinante.

Un método virtual puede ser *reemplazado* en una clase derivada. Cuando una declaración de método de instancia incluye un modificador "override", el método reemplaza un método virtual heredado con la misma signatura. Mientras que una declaración de método virtual introduce un método nuevo, una declaración de método de reemplazo especializa un método virtual heredado existente proporcionando una nueva implementación de ese método.

Un *método abstracto* es un método virtual sin implementación. Un método abstracto se declara con el modificador "abstract" y solo se permite en una clase que también se declare abstracta. Un método abstracto debe reemplazarse en todas las clases derivadas no abstractas.

En el ejemplo siguiente se declara una clase abstracta, `Expression`, que representa un nodo de árbol de expresión y tres clases derivadas, `Constant`, `VariableReference` y `Operation`, que implementan nodos de árbol de expresión para constantes, referencias a variables y operaciones aritméticas. (Este ejemplo es similar a los tipos de árbol de expresión, pero no debe confundirse con ellos).

[!code-csharp[ExpressionClass](~/samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L3-L61)]

Las cuatro clases anteriores se pueden usar para modelar expresiones aritméticas. Por ejemplo, usando instancias de estas clases, la expresión `x + 3` se puede representar de la manera siguiente.

[!code-csharp[ExpressionExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L40-L43)]

El método `Evaluate` de una instancia `Expression` se invoca para evaluar la expresión determinada y generar un valor `double`. El método toma un argumento `Dictionary` que contiene nombres de variables (como claves de las entradas) y valores (como valores de las entradas). Como `Evaluate` es un método abstracto, las clases no abstractas que derivan de `Expression` deben invalidar `Evaluate`.

Una implementación de `Constant` de `Evaluate` simplemente devuelve la constante almacenada. Una implementación de `VariableReference` busca el nombre de variable en el diccionario y devuelve el valor resultante. Una implementación de `Operation` evalúa primero los operandos izquierdo y derecho (mediante la invocación recursiva de sus métodos `Evaluate`) y luego realiza la operación aritmética correspondiente.

El siguiente programa usa las clases `Expression` para evaluar la expresión `x * (y + 2)` para los distintos valores de `x` y `y`.

[!code-csharp[ExpressionUsage](~/samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L66-L89)]

### <a name="method-overloading"></a>Sobrecarga de métodos

La *sobrecarga* de métodos permite que varios métodos de la misma clase tengan el mismo nombre mientras tengan signaturas únicas. Al compilar una invocación de un método sobrecargado, el compilador usa la *resolución de sobrecarga* para determinar el método concreto que de invocará. La resolución de sobrecarga busca el método que mejor coincida con los argumentos o informa de un error si no se puede encontrar ninguna mejor coincidencia. En el ejemplo siguiente se muestra la resolución de sobrecarga en vigor. El comentario para cada invocación del método `UsageExample` muestra qué método se invoca.

[!code-csharp[OverloadUsage](~/samples/snippets/csharp/tour/classes-and-objects/Overloading.cs#L3-L41)]

Tal como se muestra en el ejemplo, un método determinado siempre se puede seleccionar mediante la conversión explícita de los argumentos en los tipos de parámetros exactos o el suministro explícito de los argumentos de tipo.

## <a name="other-function-members"></a>Otros miembros de función

Los miembros que contienen código ejecutable se conocen colectivamente como *miembros de función* de una clase. En la sección anterior se describen los métodos, que son los tipos principales de los miembros de función. En esta sección se describen los otros tipos de miembros de función admitidos por C#: constructores, propiedades, indexadores, eventos, operadores y finalizadores.

En el ejemplo siguiente se muestra una clase genérica llamada `MyList<T>`, que implementa una lista creciente de objetos. La clase contiene varios ejemplos de los tipos más comunes de miembros de función.

> [!NOTE]
> Este ejemplo crea una clase `MyList`, que no es la misma que la clase <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> estándar de .NET. Ilustra los conceptos necesarios para esta guía, pero no sustituye a esa clase.

[!code-csharp[ListClass](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L4-L89)]

### <a name="constructors"></a>Constructores

C# admite constructores de instancia y estáticos. Un *constructor de instancia* es un miembro que implementa las acciones necesarias para inicializar una instancia de una clase. Un *constructor estático* es un miembro que implementa las acciones necesarias para inicializar una clase en sí misma cuando se carga por primera vez.

Un constructor se declara como un método sin ningún tipo de valor devuelto y el mismo nombre que la clase contenedora. Si una declaración de constructor incluye un modificador "static", declara un constructor estático. De lo contrario, declara un constructor de instancia.

Los constructores de instancia pueden sobrecargarse y tener parámetros opcionales. Por ejemplo, la clase `MyList<T>` declara un constructor de instancia con único parámetro `int` opcional. Los constructores de instancia se invocan mediante el operador `new`. Las siguientes instrucciones asignan dos instancias `MyList<string>` mediante el constructor de la clase `MyList` con y sin el argumento opcional.

[!code-csharp[ListExample1](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L95-L96)]

A diferencia de otros miembros, los constructores de instancia no se heredan y una clase no tiene ningún constructor de instancia que no sea el que se declara realmente en la clase. Si no se proporciona ningún constructor de instancia para una clase, se proporciona automáticamente uno vacío sin ningún parámetro.

### <a name="properties"></a>Propiedades

Las *propiedades* son una extensión natural de los campos. Ambos son miembros con nombre con tipos asociados y la sintaxis para acceder a los campos y las propiedades es la misma. Pero a diferencia de los campos, las propiedades no denotan ubicaciones de almacenamiento. Las propiedades tienen *descriptores de acceso* que especifican las instrucciones que se ejecutan cuando se leen o escriben sus valores.

Una propiedad se declara como un campo, salvo que la declaración finaliza con un descriptor de acceso get y un descriptor de acceso set escrito entre los delimitadores `{` y `}` en lugar de finalizar en un punto y coma. Una propiedad que tiene un descriptor de acceso get y un descriptor de acceso set es una *propiedad de lectura y escritura*, una propiedad que tiene solo un descriptor de acceso get es una *propiedad de solo lectura* y una propiedad que tiene solo un descriptor de acceso set es una *propiedad de solo escritura*.

Un descriptor de acceso get corresponde a un método sin parámetros con un valor devuelto del tipo de propiedad. Excepto como destino de una asignación, cuando se hace referencia a una propiedad en una expresión, el descriptor de acceso get de la propiedad se invoca para calcular el valor de la propiedad.

Un descriptor de acceso set corresponde a un método con un solo parámetro denominado value y ningún tipo de valor devuelto. Cuando se hace referencia a una propiedad como el destino de una asignación o como el operando de ++ o--, el descriptor de acceso set se invoca con un argumento que proporciona el nuevo valor.

La clase `MyList<T>` declara dos propiedades, `Count` y `Capacity`, que son de solo lectura y de lectura y escritura, respectivamente. El código siguiente es un ejemplo de uso de estas propiedades:

[!code-csharp[ListExample2](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L101-L104)]

De forma similar a los campos y métodos, C# admite propiedades de instancia y propiedades estáticas. Las propiedades estáticas se declaran con el modificador "static", y las propiedades de instancia se declaran sin él.

Los descriptores de acceso de una propiedad pueden ser virtuales. Cuando una declaración de propiedad incluye un modificador `virtual`, `abstract` o `override`, se aplica a los descriptores de acceso de la propiedad.

### <a name="indexers"></a>Indizadores

Un *indexador* es un miembro que permite indexar de la misma manera que una matriz. Un indexador se declara como una propiedad, excepto por el hecho que el nombre del miembro es `this`, seguido por una lista de parámetros que se escriben entre los delimitadores `[` y `]`. Los parámetros están disponibles en los descriptores de acceso del indexador. De forma similar a las propiedades, los indexadores pueden ser lectura y escritura, de solo lectura y de solo escritura, y los descriptores de acceso de un indexador pueden ser virtuales.

La clase `MyList<T>` declara un único indexador de lectura y escritura que toma un parámetro `int`. El indexador permite indexar instancias de `MyList<T>` con valores `int`. Por ejemplo:

[!code-csharp[ListExample3](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L109-L117)]

Los indexadores se pueden sobrecargar, lo que significa que una clase puede declarar varios indexadores siempre y cuando el número o los tipos de sus parámetros sean diferentes.

### <a name="events"></a>Events

Un *evento* es un miembro que permite que una clase u objeto proporcionen notificaciones. Un evento se declara como un campo, excepto por el hecho de que la declaración incluye una palabra clave event y el tipo debe ser un tipo delegado.

Dentro de una clase que declara un miembro de evento, el evento se comporta como un campo de un tipo delegado (siempre que el evento no sea abstracto y no declare descriptores de acceso). El campo almacena una referencia a un delegado que representa los controladores de eventos que se han agregado al evento. Si no existen controladores de eventos, el campo es `null`.

La clase `MyList<T>` declara un único miembro de evento llamado `Changed`, lo que indica que se ha agregado un nuevo elemento a la lista. El método virtual `OnChanged` genera el evento cambiado, y comprueba primero si el evento es `null` (lo que significa que no existen controladores). La noción de generar un evento es equivalente exactamente a invocar el delegado representado por el evento; por lo tanto, no hay ninguna construcción especial de lenguaje para generar eventos.

Los clientes reaccionan a los eventos mediante *controladores de eventos*. Los controladores de eventos se asocian mediante el operador `+=` y se quitan con el operador `-=`. En el ejemplo siguiente se asocia un controlador de eventos con el evento `Changed` de un objeto `MyList<string>`.

[!code-csharp[EventExample](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L132-L148)]

Para escenarios avanzados donde se quiere controlar el almacenamiento subyacente de un evento, una declaración de evento puede proporcionar de forma explícita los descriptores de acceso `add` y `remove`, que son similares al descriptor de acceso `set` de una propiedad.

### <a name="operators"></a>Operadores

Un *operador* es un miembro que define el significado de aplicar un operador de expresión determinado a las instancias de una clase. Se pueden definir tres tipos de operadores: operadores unarios, operadores binarios y operadores de conversión. Todos los operadores se deben declarar como `public` y `static`.

La clase `MyList<T>` declara dos operadores, `operator ==` y `operator !=`, y de este modo proporciona un nuevo significado a expresiones que aplican esos operadores a instancias `MyList`. En concreto, los operadores definen la igualdad de dos instancias `MyList<T>` como la comparación de cada uno de los objetos contenidos con sus métodos Equals. En el ejemplo siguiente se usa el operador `==` para comparar dos instancias `MyList<int>`.

[!code-csharp[OperatorExample](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L121-L129)]

El primer objeto `Console.WriteLine` genera `True` porque las dos listas contienen el mismo número de objetos con los mismos valores en el mismo orden. Si `MyList<T>` no hubiera definido `operator ==`, el primer objeto `Console.WriteLine` habría generado `False` porque `a` y `b` hacen referencia a diferentes instancias de `MyList<int>`.

### <a name="finalizers"></a>Finalizadores

Un *finalizador* es un miembro que implementa las acciones necesarias para finalizar una instancia de una clase. Los finalizadores no pueden tener parámetros, no pueden tener modificadores de accesibilidad y no se pueden invocar de forma explícita. El finalizador de una instancia se invoca automáticamente durante la recolección de elementos no utilizados.

El recolector de elementos no utilizados tiene una amplia libertad para decidir cuándo debe recolectar objetos y ejecutar finalizadores. En concreto, los intervalos de las invocaciones de finalizador no son deterministas y los finalizadores se pueden ejecutar en cualquier subproceso. Por estas y otras razones, las clases deben implementar finalizadores solo cuando no haya otras soluciones que sean factibles.

La instrucción `using` proporciona un mejor enfoque para la destrucción de objetos.

> [!div class="step-by-step"]
> [Anterior](statements.md)
> [Siguiente](arrays.md)
