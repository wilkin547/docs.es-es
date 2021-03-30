---
title: Actualización del código base para usar tipos de referencia que aceptan valores NULL
description: Elija la mejor estrategia de actualización de su código base para usar tipos de referencia que aceptan valores NULL.
ms.technology: csharp-null-safety
ms.date: 07/31/2019
ms.openlocfilehash: fff9ce4d053cc2543b0148d70435bdc793ecccd7
ms.sourcegitcommit: 05d0087dfca85aac9ca2960f86c5efd218bf833f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "105637169"
---
# <a name="update-libraries-to-use-nullable-reference-types-and-communicate-nullable-rules-to-callers"></a>Actualización de las bibliotecas para usar tipos de referencia que aceptan valores NULL y comunicar reglas que aceptan valores NULL a los llamadores

La adición de [tipos de referencia que aceptan valores NULL](nullable-references.md) significa que puede declarar si se permite o espera un valor de `null` para cada variable. Además, puede aplicar varios atributos, `AllowNull`, `DisallowNull`, `MaybeNull`, `NotNull`, `NotNullWhen`, `MaybeNullWhen` y `NotNullIfNotNull`, para describir por completo los estados NULL de los valores devueltos y de argumento. Esto proporciona una gran experiencia de escritura de código. Por ejemplo, obtiene advertencias si una variable que no acepta valores NULL está establecida en `null`. También recibe advertencias si no se comprueban los valores NULL de una variable que acepta valores NULL antes de desreferenciarla. La actualización de las bibliotecas puede llevar un tiempo, pero merece la pena. Cuanta más información proporcione al compilador sobre *cuándo* está permitido o prohibido un valor `null`, mejores advertencias obtendrán los usuarios de la API. Para empezar, se usará un ejemplo conocido. Imagine que la biblioteca tiene la siguiente API para recuperar una cadena de recursos:

```csharp
bool TryGetMessage(string key, out string message)
```

En el ejemplo anterior se sigue el conocido patrón de `Try*` en .NET. Hay dos argumentos de referencia para esta API: los parámetros `key` y `message`. Esta API tiene las siguientes reglas relacionadas con la obtención del valor NULL de estos argumentos:

- Los autores de la llamada no deben pasar `null` como argumento para `key`.
- Los autores de la llamada pueden pasar una variable cuyo valor sea `null` como argumento de `message`.
- Si el método `TryGetMessage` devuelve `true`, el valor de `message` no es NULL. Si el valor devuelto es `false,`, el valor de `message` (y su estado NULL) es NULL.

La regla para `key` se puede expresar completamente mediante el tipo de variable; `key` debe ser un tipo de referencia que no acepte valores NULL. El parámetro `message` es más complejo. Permite `null` como argumento, pero garantiza que, si se ejecuta correctamente, el argumento `out` no sea NULL. En estos escenarios, necesita un vocabulario más completo para describir las expectativas.

La actualización de la biblioteca para las referencias que aceptan valores NULL requiere más trabajo que agregar `?` en algunas de las variables y los nombres de tipo. En el ejemplo anterior se muestra que debe examinar las API y tener en cuenta las expectativas para cada argumento de entrada. Considere las garantías para el valor devuelto y cualquier argumento `out` o `ref` en la devolución del método. Después, comunique dichas reglas al compilador y este proporcionará advertencias cuando los llamadores no las cumplan.

Este trabajo lleva tiempo. Empecemos con las estrategias para hacer que su biblioteca o aplicación sea compatible con valores NULL, a la vez que equilibra otros requisitos. Verá cómo equilibrar el desarrollo continuo habilitando tipos de referencia que admiten valores NULL. Conocerá los desafíos de las definiciones de tipo genérico. Y aprenderá a aplicar atributos para describir condiciones previas y posteriores en las API individuales.

## <a name="choose-a-strategy-for-nullable-reference-types"></a>Elección de una estrategia para admitir tipos de referencia que aceptan valores NULL

Primero debe elegir si los tipos de referencia que aceptan valores NULL deben estar habilitados o desactivados de forma predeterminada. Tiene dos estrategias:

- Habilitar los tipos de referencia que aceptan valores NULL para todo el proyecto y deshabilitarlos en el código que no está listo.
- Habilitar solo los tipos de referencia que aceptan valores NULL para el código que se ha anotado para estos tipos de referencia.

La primera estrategia funciona mejor si va a agregar otras características a la biblioteca a medida que la actualiza para admitir tipos de referencia que aceptan valores NULL. Todo el desarrollo nuevo es compatible con valores NULL. Al actualizar el código existente, se habilitan los tipos de referencia que aceptan valores NULL en esas clases.

Para seguir esta primera estrategia, realice los pasos siguientes:

1. Habilite los tipos de referencia que aceptan valores NULL para todo el proyecto agregando el elemento `<Nullable>enable</Nullable>` a los archivos *csproj*.
1. Agregue la pragma `#nullable disable` a cada archivo de código fuente del proyecto.
1. A la hora de trabajar en cada archivo, quite la pragma y resuelva las advertencias.

Esta primera estrategia requiere más trabajo previo para agregar la pragma a cada archivo. La ventaja es que todos los archivos de código nuevos que se agreguen al proyecto estarán habilitados para aceptar valores NULL. Cualquier trabajo nuevo admitirá valores NULL; solo se debe actualizar el código existente.

La segunda estrategia funciona mejor si la biblioteca es estable y el objetivo principal del desarrollo es adoptar tipos de referencia que aceptan valores NULL. Los tipos de referencia que aceptan valores NULL se habilitan al anotar las API. Cuando haya terminado, habilite los tipos de referencia que aceptan valores NULL para todo el proyecto.

Para seguir esta segunda estrategia, realice los pasos siguientes:

1. Agregue la pragma `#nullable enable` al archivo que quiere que admita valores NULL.
1. Resuelva las advertencias.
1. Continúe con estos dos primeros pasos hasta que la biblioteca entera sea compatible con valores NULL.
1. Agregue el elemento `<Nullable>enable</Nullable>` a los archivos *csproj* para habilitar los tipos que aceptan valores NULL para todo el proyecto.
1. Quite las pragmas `#nullable enable`, puesto que ya no son necesarias.

Esta segunda estrategia requiere menos trabajo previo. La desventaja es que la primera tarea al crear un nuevo archivo consiste en agregar la pragma y hacer que admita valores NULL. Si alguno de los desarrolladores de su equipo se olvida de hacerlo, ese nuevo código se sumará al trabajo pendiente para hacer que todo el código admita valores NULL.

La elección de una estrategia u otra dependerá de la cantidad de desarrollo activo que haya en el proyecto. Cuanto más desarrollado esté y más estable sea su proyecto, más adecuada será la segunda estrategia. Cuantas más características se estén desarrollando, más apropiada será la primera estrategia.

> [!IMPORTANT]
> El contexto global que admite un valor NULL no se aplica a los archivos de código generado. En cualquier estrategia, el contexto que admite un valor NULL está *deshabilitado* para cualquier archivo de código fuente marcado como generado. Esto significa que las API de los archivos generados no se anotan. Hay cuatro maneras de marcar un archivo como generado:
>
> 1. En el archivo .editorconfig, especifique `generated_code = true` en una sección que se aplique a ese archivo.
> 1. Coloque `<auto-generated>` o `<auto-generated/>` en un comentario en la parte superior del archivo. Puede estar en cualquier línea de ese comentario, pero el bloque de comentario debe ser el primer elemento del archivo.
> 1. Inicie el nombre de archivo con *TemporaryGeneratedFile_*
> 1. Finalice el nombre de archivo con *.designer.cs*, *.generated.cs*, *.g.cs* o *.g.i.cs*.
>
> Los generadores pueden optar por usar la directiva de preprocesador [`#nullable`](language-reference/preprocessor-directives.md#nullable-context).

## <a name="should-nullable-warnings-introduce-breaking-changes"></a>¿Deberían introducir cambios importantes las advertencias que aceptan valores NULL?

Antes de habilitar los tipos de referencia que aceptan valores NULL, se considera que las variables *desconocen los valores NULL*. Una vez habilitados los tipos de referencia que aceptan valores NULL, todas esas variables *no aceptan valores NULL*. El compilador generará advertencias si dichas variables se inicializan en valores que sean NULL.

Otra posible causa de que se generen advertencias es la devolución de valores cuando los valores no se han inicializado.

El primer paso para abordar las advertencias del compilador es usar anotaciones `?` en los tipos de parámetros y de valores devueltos para indicar si los argumentos o los valores devueltos pueden ser NULL. Cuando las variables de referencia no deben ser NULL, la declaración original es correcta. A medida que realiza esta tarea, su objetivo no es solo resolver las advertencias; el objetivo más importante es hacer que el compilador entienda su intención de admitir posibles valores NULL. Cuando examine las advertencias, llegará a la siguiente decisión importante que debe tomar para la biblioteca. ¿Quiere modificar las firmas de API para comunicar con mayor claridad su intención de diseño? Una mejor firma de API para el método `TryGetMessage` examinado anteriormente podría ser la siguiente:

```csharp
string? TryGetMessage(string key);
```

El valor devuelto indica si la acción se ha realizado correctamente o no y contiene el valor si se ha encontrado. En muchos casos, cambiar las firmas de API puede mejorar el modo en que comunican los valores NULL.

Pero en el caso de las bibliotecas públicas o con grandes bases de usuarios, puede que prefiera no introducir ningún cambio en las firmas de API. En esos casos, y en otros patrones comunes, puede aplicar atributos para definir con más claridad cuándo puede ser `null` un argumento o un valor devuelto. Tanto si cambia la superficie de la API como si no, probablemente verá que las anotaciones de tipo por sí solas no son suficientes para describir valores `null` para argumentos o valores devueltos. En esos casos, puede aplicar atributos para describir una API de forma más clara.

## <a name="attributes-extend-type-annotations"></a>Atributos para complementar a las anotaciones de tipo

Se han agregado varios atributos para expresar información adicional sobre el estado NULL de las variables. Todo el código escrito antes de que C# 8 introdujera los tipos de referencia que aceptan valores NULL *desconocía los valores NULL*. Esto significa que es posible que cualquier variable de tipo de referencia sea NULL, pero no se necesitan comprobaciones de valores NULL. Una vez que el código *admite valores NULL*, esas reglas cambian. Los tipos de referencia nunca deben ser del valor `null`, y los que admitan valores NULL se deben comprobar con `null` antes de desreferenciarlos.

Es probable que las reglas de las API sean más complicadas, como se ha visto en el escenario de la API `TryGetValue`. Muchas de las API tienen reglas más complejas para cuando las variables pueden ser `null` o no. En estos casos, usará atributos para expresar dichas reglas. Los atributos que describen la semántica de la API se encuentran en el artículo sobre los [atributos que afectan al análisis del estado NULL](./language-reference/attributes/nullable-analysis.md).

## <a name="generic-definitions-and-nullability"></a>Definiciones genéricas y nulabilidad

Para comunicar correctamente el estado NULL de los tipos y métodos genéricos es necesario prestar especial atención. Esta atención extra se debe a que un tipo de valor que acepta valores NULL y un tipo de referencia que acepta valores NULL son muy diferentes. Un `int?` es un sinónimo de `Nullable<int>`, mientras que `string?` es lo mismo que `string` con un atributo agregado por el compilador. El resultado es que el compilador no puede generar código correcto para `T?` sin saber si `T` es un objeto `class` o `struct`.

Esto no significa que no pueda usar un tipo que acepta valores NULL (ya sea un tipo de valor o un tipo de referencia) como argumento de tipo para un tipo genérico cerrado. Tanto `List<string?>` como `List<int?>` son instancias válidas de `List<T>`.

Lo que significa es que no se puede usar `T?` en una declaración de método o clase genérica sin restricciones. Por ejemplo, <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable%7B%60%600%7D)?displayProperty=nameWithType> no se cambiará para devolver `T?`. Puede superar esta limitación agregando las restricciones `struct` o `class`. Con cualquiera de estas restricciones, el compilador sabe cómo generar código para `T` y `T?`.

Es posible que quiera restringir los tipos usados para un argumento de tipo genérico a tipos que no aceptan valores NULL. Para ello, agregue la restricción `notnull` a ese argumento de tipo. Cuando se aplica esta restricción, el argumento de tipo no debe ser un tipo que acepta valores NULL.

## <a name="late-initialized-properties-data-transfer-objects-and-nullability"></a>Propiedades inicializadas con posterioridad, objetos de transferencia de datos y nulabilidad

Para indicar la nulabilidad de las propiedades inicializadas con posterioridad, es decir, establecidas después de la construcción, puede que deba prestar especial atención para asegurarse de que la clase sigue expresando correctamente la intención de diseño original.

A menudo se crean instancias de tipos que contienen propiedades inicializadas con posterioridad, como objetos de transferencia de datos (DTO), mediante una biblioteca externa, por ejemplo, un ORM (asignador relacional de objetos) de base de datos, un deserializador u otro componente que rellena automáticamente las propiedades a partir de otro origen.

Fíjese en la siguiente clase de DTO, la cual representa a un estudiante, antes de habilitar los tipos de referencia que aceptan valores NULL:

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string VehicleRegistration { get; set; }
}
```

La intención de diseño (indicada en este caso por el atributo `Required`) sugiere que, en este sistema, las propiedades `FirstName` y `LastName` son **obligatorias** y, por tanto, no son NULL.

La propiedad `VehicleRegistration` **no es obligatoria**, por lo que puede ser NULL.

Cuando se habilitan tipos de referencia que aceptan valores NULL, se debe indicar qué propiedades de DTO podrían admitir valores NULL, de acuerdo con la intención original:

```csharp
class Student
{
    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

Para este DTO, la única propiedad que puede ser NULL es ``VehicleRegistration``.

A pesar de esto, el compilador genera advertencias `CS8618` para `FirstName` y `LastName` para indicar que las propiedades que no aceptan valores NULL no están inicializadas.

Hay tres opciones disponibles para resolver las advertencias del compilador de una manera que mantiene la intención original. Cualquiera de estas opciones es válida y debe elegir la que mejor se adapte a sus requisitos de diseño y su estilo de codificación.

### <a name="initialize-in-the-constructor"></a>Inicializar en el constructor

La forma ideal de resolver las advertencias de propiedades no inicializadas es inicializar las propiedades en el constructor:

```csharp
class Student
{
    public Student(string firstName, string lastName)
    {
        FirstName = firstName;
        LastName = lastName;
    }

    [Required]
    public string FirstName { get; set; }

    [Required]
    public string LastName { get; set; }

    public string? VehicleRegistration { get; set; }
}
```

Este enfoque únicamente funciona si la biblioteca que se usa para crear instancias de la clase admite el paso de parámetros en el constructor.

Una biblioteca puede admitir el paso de *algunas* propiedades en el constructor, pero no todas. Por ejemplo, EF Core admite el [enlace del constructor](/ef/core/modeling/constructors) para las propiedades de columna normales, pero no para las propiedades de navegación.

Consulte la documentación de la biblioteca que crea instancias de la clase para comprender en qué medida admite el enlace del constructor.

### <a name="property-with-nullable-backing-field"></a>Propiedad con campo de respaldo que acepta valores NULL

Si el enlace del constructor no funcionara en su caso, una manera de solucionar este problema sería tener una propiedad que no acepta valores NULL con un campo de respaldo que acepta valores NULL:

```csharp
private string? _firstName;

[Required]
public string FirstName
{
    set => _firstName = value;
    get => _firstName
           ?? throw new InvalidOperationException("Uninitialized " + nameof(FirstName))
}
```

En este escenario, si se accede a la propiedad `FirstName` antes de que se haya inicializado, el código produce una excepción `InvalidOperationException`, porque el contrato de API se ha usado incorrectamente.

Tenga en cuenta que algunas bibliotecas pueden tener requisitos especiales a la hora de usar los campos de respaldo. Por ejemplo, puede ser necesario configurar EF Core para usar los [campos de respaldo](/ef/core/modeling/backing-field) correctamente.

### <a name="initialize-the-property-to-null"></a>Inicialización de la propiedad con un valor NULL

Como alternativa al uso de un campo de respaldo que acepta valores NULL, o si la biblioteca que crea instancias de la clase no es compatible con ese enfoque, puede inicializar la propiedad como `null` directamente con la ayuda del operador que permite valores NULL (`!`):

```csharp
[Required]
public string FirstName { get; set; } = null!;

[Required]
public string LastName { get; set; } = null!;

public string? VehicleRegistration { get; set; }
```

Nunca observará un valor NULL real en tiempo de ejecución, a menos que se produzca un error de programación al acceder a la propiedad antes de que se haya inicializado correctamente.

## <a name="see-also"></a>Consulte también

- [Migración de un código base existente a referencias que aceptan valores NULL](whats-new/tutorials/upgrade-to-nullable-references.md)
- [Uso de tipos de referencia que aceptan valores NULL en EF Core](/ef/core/miscellaneous/nullable-reference-types)
