---
title: 'Atributos reservados de C#: Análisis estático que admite un valor NULL'
ms.date: 04/14/2020
description: El compilador interpreta estos atributos para proporcionar un mejor análisis estático para los tipos de referencia que aceptan y que no aceptan valores NULL.
ms.openlocfilehash: 33521133a6a01196e6e1ab9c3cdc191a24f1ecf3
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102715"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a>Los atributos reservados contribuyen al análisis estático del estado NULL del compilador.

En un contexto que admite un valor NULL, el compilador realiza un análisis estático del código para determinar el estado NULL de todas las variables de tipo de referencia:

- *not null*: el análisis estático ha determinado que a la variable se le asigna un valor distinto de NULL.
- *maybe null*: el análisis estático no puede determinar que a la variable se le asigna un valor distinto de NULL.

Puede aplicar una serie de atributos que proporcionan información al compilador sobre la semántica de las API. Esa información ayuda al compilador a realizar análisis estáticos y a determinar si una variable no es NULL. En este artículo se proporciona una breve descripción de cada uno de esos atributos y cómo usarlos. En todos los ejemplos se asume el uso de C# 8.0 o una versión más reciente, y que el código se encuentra en un contexto que admite un valor NULL.

Para empezar, se usará un ejemplo conocido. Imagine que la biblioteca tiene la siguiente API para recuperar una cadena de recursos:

```csharp
bool TryGetMessage(string key, out string message)
```

En el ejemplo anterior se sigue el conocido patrón de `Try*` en .NET. Hay dos argumentos de referencia para esta API: los parámetros `key` y `message`. Esta API tiene las siguientes reglas relacionadas con la obtención del valor NULL de estos argumentos:

- Los autores de la llamada no deben pasar `null` como argumento para `key`.
- Los autores de la llamada pueden pasar una variable cuyo valor sea `null` como argumento de `message`.
- Si el método `TryGetMessage` devuelve `true`, el valor de `message` no es NULL. Si el valor devuelto es `false,`, el valor de `message` (y su estado NULL) es NULL.

La regla para `key` se puede expresar mediante el tipo de variable: `key` debe ser un tipo de referencia que no acepte valores NULL. El parámetro `message` es más complejo. Permite `null` como argumento, pero garantiza que, si se ejecuta correctamente, el argumento `out` no sea NULL. En estos escenarios, necesita un vocabulario más completo para describir las expectativas.

Se han agregado varios atributos para expresar información adicional sobre el estado NULL de las variables. Todo el código escrito antes de que C# 8 introdujera los tipos de referencia que aceptan valores NULL *desconocía los valores NULL*. Esto significa que es posible que cualquier variable de tipo de referencia sea NULL, pero no se necesitan comprobaciones de valores NULL. Una vez que el código *admite valores NULL*, esas reglas cambian. Los tipos de referencia nunca deben ser del valor `null`, y los que admitan valores NULL se deben comprobar con `null` antes de desreferenciarlos.

Es probable que las reglas de las API sean más complicadas, como se ha visto en el escenario de la API `TryGetValue`. Muchas de las API tienen reglas más complejas para cuando las variables pueden ser `null` o no. En estos casos, usará uno de los atributos siguientes para expresar estas reglas:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): un argumento de entrada que no acepta valores NULL puede ser NULL.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argumento de entrada que admite un valor NULL nunca debe ser NULL.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): un valor devuelto que no acepta valores NULL puede ser NULL.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): un valor devuelto que admite un valor NULL nunca será NULL.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argumento de entrada que no acepta valores NULL puede ser NULL cuando el método devuelve el valor `bool` especificado.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argumento de entrada que admite un valor NULL nunca será NULL cuando el método devuelve el valor `bool` especificado.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): un valor devuelto no es NULL si el argumento del parámetro especificado no es NULL.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): un método nunca devuelve un valor. Es decir, siempre inicia una excepción.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): este método nunca devuelve un valor si el parámetro `bool` asociado tiene el valor especificado.

Las descripciones anteriores son una referencia rápida a lo que hace cada atributo. En cada una de las secciones siguientes se describen el comportamiento y el significado con más detalle.

Al agregar estos atributos, se proporciona más información al compilador sobre las reglas de la API. Cuando el código que realiza la llamada se compila en un contexto habilitado para aceptar valores NULL, el compilador advertirá a los autores de la llamada cuando infrinjan esas reglas. Estos atributos no habilitan comprobaciones adicionales en la implementación.

## <a name="specify-preconditions-allownull-and-disallownull"></a>Especificación de condiciones previas: `AllowNull` y `DisallowNull`

Considere una propiedad de lectura y escritura que nunca devuelve `null` porque tiene un valor predeterminado razonable. Los autores de la llamada pasan `null` al descriptor de acceso set cuando lo establecen en el valor predeterminado. Por ejemplo, imagine un sistema de mensajería que solicita un nombre de pantalla en un salón de chat. Si no se proporciona ninguno, el sistema genera uno aleatorio:

```csharp
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName;
```

Al compilar el código anterior en un contexto en el que se desconocen los valores NULL, todo es correcto. Una vez que se habilitan los tipos de referencia que admiten un valor NULL, la propiedad `ScreenName` se convierte en una referencia que no acepta valores NULL. Eso es correcto para el descriptor de acceso `get`: nunca devuelve `null`. No es necesario que los autores de la llamada comprueben `null` en la propiedad devuelta. Pero ahora, al establecer la propiedad en `null`, se genera una advertencia. Para continuar admitiendo este tipo de código, agregue el atributo <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> a la propiedad, como se muestra en el código siguiente:

```csharp
[AllowNull]
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName = GenerateRandomScreenName();
```

Es posible que tenga que agregar una directiva `using` para <xref:System.Diagnostics.CodeAnalysis> a fin de usar este y otros atributos descritos en este artículo. El atributo se aplica a la propiedad, no al descriptor de acceso `set`. El atributo `AllowNull` especifica *condiciones previas* y solo se aplica a las entradas. El descriptor de acceso `get` tiene un valor devuelto, pero no tiene argumentos de entrada. Por tanto, el atributo `AllowNull` solo se aplica al descriptor de acceso `set`.

En el ejemplo anterior se muestra qué se debe buscar al agregar el atributo `AllowNull` en un argumento:

1. El contrato general para esa variable es que no debe ser `null`, por lo que quiere un tipo de referencia que no acepte valores NULL.
1. Hay escenarios para que la variable de entrada sea `null`, aunque no sean el uso más común.

En la mayoría de los casos necesitará este atributo para las propiedades, o bien para los argumentos `in`, `out` y `ref`. El atributo `AllowNull` es la mejor opción cuando una variable normalmente no es NULL, pero debe permitir `null` como condición previa.

Compare esto con los escenarios para usar `DisallowNull`: este atributo se usa para especificar que una variable de entrada de un tipo de referencia que admite un valor NULL no debe ser `null`. Considere una propiedad donde `null` es el valor predeterminado, pero los clientes solo pueden establecerla en un valor que no sea NULL. Observe el código siguiente:

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

El código anterior es la mejor manera de expresar el diseño de que `ReviewComment` pueda ser `null`, pero no se puede establecer en `null`. Una vez que este código admita valores NULL, puede expresar este concepto con más claridad para los autores de la llamada mediante <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>:

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

En un contexto que admite un valor NULL, el descriptor de acceso `get` de `ReviewComment` podría devolver el valor predeterminado de `null`. El compilador advierte que se debe comprobar antes del acceso. Además, advierte a los autores de la llamada que, aunque podría ser `null`, no deberían establecerlo de forma explícita en `null`. El atributo `DisallowNull` también especifica una *condición previa*, no afecta al descriptor de acceso `get`. Use el atributo `DisallowNull` cuando observe estas características:

1. La variable podría ser `null` en escenarios principales, a menudo cuando se crea su primera instancia.
1. La variable no se debe establecer de forma explícita en `null`.

Estas situaciones son comunes en el código en el que originalmente *se desconocían los valores NULL*. Es posible que las propiedades de objeto se establezcan en dos operaciones de inicialización distintas. Es posible que algunas propiedades se establezcan solo después de que se haya completado algún trabajo asincrónico.

Los atributos `AllowNull` y `DisallowNull` permiten especificar que las condiciones previas de las variables puedan no coincidir con las anotaciones que admiten un valor NULL en esas variables. Proporcionan más detalles sobre las características de la API. Esta información adicional ayuda a los autores de la llamada a usar la API de manera correcta. Recuerde que debe especificar las condiciones previas mediante los atributos siguientes:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): un argumento de entrada que no acepta valores NULL puede ser NULL.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argumento de entrada que admite un valor NULL nunca debe ser NULL.

## <a name="specify-post-conditions-maybenull-and-notnull"></a>Especificación de condiciones posteriores: `MaybeNull` y `NotNull`

Imagine que tiene un método con la siguiente firma:

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

Probablemente haya escrito un método como este para devolver `null` cuando no se encuentra el nombre que se busca. `null` indica claramente que no se ha encontrado el registro. En este ejemplo, es probable que cambie el tipo de valor devuelto de `Customer` a `Customer?`. Al declarar el valor devuelto como un tipo de referencia que admite un valor NULL, se especifica claramente la intención de esta API.

Por los motivos descritos en [Definiciones genéricas y nulabilidad](../../nullable-migration-strategies.md#generic-definitions-and-nullability), esa técnica no funciona con los métodos genéricos. Puede tener un método genérico que siga un patrón similar:

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

No puede especificar que el valor devuelto sea `T?`. El método devuelve `null` cuando no se encuentra el elemento buscado. Como no puede declarar un tipo de valor devuelto `T?`, agregue la anotación `MaybeNull` al valor devuelto del método:

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

El código anterior informa a los autores de la llamada de que el contrato implica un tipo que no acepta valores NULL, pero el valor devuelto *puede* realmente ser NULL.  Use el atributo `MaybeNull` cuando la API deba ser un tipo que no acepta valores NULL, normalmente un parámetro de tipo genérico, pero puede haber casos en los que se devuelva `null`.

También puede especificar que un valor devuelto o un argumento `out` o `ref` no sea NULL aunque el tipo sea un tipo de referencia que admite un valor NULL. Considere un método que garantiza que una matriz es lo suficientemente grande como para contener un número de elementos. Si el argumento de entrada no tiene capacidad, la rutina asignará una nueva matriz y copiará todos los elementos existentes en ella. Si el argumento de entrada es `null`, la rutina asignará un almacenamiento nuevo. Si hay capacidad suficiente, la rutina no hace nada:

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

Puede llamar a esta rutina de esta forma:

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

Después de habilitar los tipos de referencia NULL, querrá asegurarse de que el código anterior se compila sin advertencias. Cuando el método devuelve un valor, se garantiza que el argumento `storage` no es NULL. Pero es aceptable llamar a `EnsureCapacity` con una referencia nula. Puede convertir a `storage` en un tipo de referencia que acepte valores NULL y agregar la condición posterior `NotNull` a la declaración del parámetro:

```csharp
public void EnsureCapacity<T>([NotNull]ref T[]? storage, int size)
```

En el código anterior se expresa con claridad el contrato existente: Los autores de la llamada pueden pasar una variable con el valor `null`, pero se garantiza que el valor devuelto nunca será NULL. El atributo `NotNull` es muy útil para los argumentos `ref` y `out`, donde `null` se puede pasar como argumento, pero se garantiza que ese argumento no será NULL cuando el método devuelva un valor.

Las condiciones posteriores condicionales se especifican mediante los atributos siguientes:

- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): un valor devuelto que no acepta valores NULL puede ser NULL.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): un valor devuelto que admite un valor NULL nunca será NULL.

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a>Especificación de condiciones posteriores condicionales: `NotNullWhen`, `MaybeNullWhen` y `NotNullIfNotNull`

Es probable que esté familiarizado con el método `string` de <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>. Este método devuelve `true` cuando el argumento es NULL o una cadena vacía. Es una forma de comprobación de valores NULL: No es necesario que los autores de la llamada comprueben los valores NULL del argumento si el método devuelve `false`. Para hacer que un método como este admita valores NULL, tendría que establecer el argumento en un tipo de referencia que admite un valor NULL y agregar el atributo `NotNullWhen`:

```csharp
bool IsNullOrEmpty([NotNullWhen(false)]string? value);
```

Esto informa al compilador de que no es necesario comprobar los valores NULL en el código cuyo valor devuelto sea `false`. La adición del atributo informa al análisis estático del compilador que `IsNullOrEmpty` realiza la comprobación de valores NULL necesaria: cuando devuelve `false`, el argumento de entrada no es `null`.

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

El método <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> se anotará como se ha mostrado antes para .NET Core 3.0. Es posible que tenga métodos similares en el código base que comprueben valores NULL en el estado de los objetos. El compilador no reconocerá los métodos de comprobación de valores NULL personalizados y tendrá que agregar personalmente las anotaciones. Al agregar el atributo, el análisis estático del compilador sabe cuándo se han comprobado los valores NULL en la variable.

Otro uso de estos atributos es el patrón `Try*`. Las condiciones posteriores para las variables `ref` y `out` se comunican a través del valor devuelto. Observe este método mostrado antes:

```csharp
bool TryGetMessage(string key, out string message)
```

El método anterior sigue una expresión de .NET típica: el valor devuelto indica si `message` se ha establecido en el valor encontrado o, si no se ha encontrado ningún mensaje, en el valor predeterminado. Si el método devuelve `true`, el valor de `message` no es NULL; de lo contrario, el método establece `message` en NULL.

Puede comunicar esa expresión mediante el atributo `NotNullWhen`. Al actualizar la firma para los tipos de referencia que admiten un valor NULL, convierta `message` en `string?` y agregue un atributo:

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

En el ejemplo anterior, se sabe que el valor de `message` no es NULL cuando `TryGetMessage` devuelve `true`. Debe anotar de la misma forma los métodos similares en el código base: los argumentos pueden ser `null`, y se sabe que no son NULL cuando el método devuelve `true`.

Hay un atributo final que también puede necesitar. En ocasiones, el estado NULL de un valor devuelto depende del estado NULL de uno o más argumentos de entrada. Estos métodos devolverán un valor no NULL siempre que determinados argumentos de entrada no sean `null`. Para anotar correctamente estos métodos, use el atributo `NotNullIfNotNull`. Observe el método siguiente:

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

Si el argumento `url` no es NULL, el resultado no es `null`. Una vez que se hayan habilitado las referencias nulas, esa firma funcionará correctamente, siempre que la API no acepte nunca una entrada NULL. Pero si la entrada puede ser NULL, el valor devuelto también podría serlo. Por tanto, podría cambiar la firma por el código siguiente:

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

Esto también funciona, pero a menudo obliga a los autores de la llamada a implementar comprobaciones de `null` adicionales. El contrato es que el valor devuelto solo será `null` cuando el argumento de entrada `url` sea `null`. Para expresar ese contrato, tendría que anotar este método como se muestra en el código siguiente:

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

El valor devuelto y el argumento se han anotado con `?`, lo que indica que cualquiera podría ser `null`. El atributo aclara todavía más que el valor devuelto no será NULL cuando el argumento `url` no sea `null`.

Las condiciones posteriores condicionales se especifican mediante estos atributos:

- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argumento de entrada que no acepta valores NULL puede ser NULL cuando el método devuelve el valor `bool` especificado.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argumento de entrada que admite un valor NULL nunca será NULL cuando el método devuelva el valor `bool` especificado.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): un valor devuelto no es NULL si el argumento de entrada del parámetro especificado no es NULL.

## <a name="verify-unreachable-code"></a>Comprobación de código inaccesible

Algunos métodos, normalmente los asistentes de excepciones u otros métodos de utilidad, siempre salen mediante el inicio de una excepción. O bien, un asistente puede iniciar una excepción basada en el valor de un argumento booleano.

En el primer caso, puede agregar el atributo `DoesNotReturn` a la declaración del método. El compilador le ayuda de tres maneras. En primer lugar, emite una advertencia si hay una ruta de acceso por la que el método puede salir sin iniciar una excepción. En segundo lugar, el compilador marca cualquier código después de una llamada a ese método como *inaccesible*, hasta que se encuentre una cláusula `catch` adecuada. Por último, el código inaccesible no afectará a ningún estado NULL. Considere este método:

```csharp
[DoesNotReturn]
private void FailFast()
{
   throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   if (!isInitialized)
      FailFast();

   // unreachable code:
   this.field = containedField;
}
```

En el segundo caso, se agrega el atributo `DoesNotReturnIf` a un parámetro booleano del método. Puede modificar el ejemplo anterior de esta manera:

```csharp
private void FailFast([DoesNotReturnIf(false)]bool isValid)
{
   if (!isValid)
       throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   FailFast(isInitialized);

   // unreachable code when "isInitialized" is false:
   this.field = containedField;
}
```

## <a name="summary"></a>Resumen

Agregar tipos de referencia que aceptan valores NULL proporciona un vocabulario inicial para describir las expectativas de las API para las variables que podrían ser `null`. Los atributos adicionales proporcionan un vocabulario más completo para describir el estado NULL de las variables como condiciones previas y posteriores. Estos atributos describen con más claridad las expectativas y proporcionan una mejor experiencia para los desarrolladores que usan las API.

A medida que actualice las bibliotecas para un contexto que admite un valor NULL, agregue estos atributos para guiar a los usuarios de las API al uso correcto. Estos atributos ayudan a describir de forma completa el estado NULL de los argumentos de entrada y los valores devueltos:

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): un argumento de entrada que no acepta valores NULL puede ser NULL.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): un argumento de entrada que admite un valor NULL nunca debe ser NULL.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): un valor devuelto que no acepta valores NULL puede ser NULL.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): un valor devuelto que admite un valor NULL nunca será NULL.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): un argumento de entrada que no acepta valores NULL puede ser NULL cuando el método devuelve el valor `bool` especificado.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): un argumento de entrada que admite un valor NULL nunca será NULL cuando el método devuelva el valor `bool` especificado.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): un valor devuelto no es NULL si el argumento de entrada del parámetro especificado no es NULL.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): un método nunca devuelve un valor. Es decir, siempre inicia una excepción.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): este método nunca devuelve un valor si el parámetro `bool` asociado tiene el valor especificado.
