---
title: Tipos de referencia que aceptan valores NULL
description: En este artículo se proporciona información general sobre los tipos de referencia que aceptan valores NULL, una novedad de C# 8.0. Conocerá cómo esta característica proporciona protección contra excepciones de referencia NULL, tanto para proyectos nuevos como para los existentes.
ms.technology: csharp-null-safety
ms.date: 04/21/2020
ms.openlocfilehash: da3b75b28d7501e8436d29c0c325c550f0a44c93
ms.sourcegitcommit: 05d0087dfca85aac9ca2960f86c5efd218bf833f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "105637173"
---
# <a name="nullable-reference-types"></a>Tipos de referencia que aceptan valores NULL

Una de las novedades de C# 8.0 son los **tipos de referencia que aceptan valores NULL** y los **tipos de referencia que no aceptan valores NULL**, que permiten usar instrucciones importantes sobre las propiedades de variables de tipos de referencia:

- **Se supone que una referencia no debe ser NULL**. Si las variables no deben ser NULL, el compilador aplica reglas que garantizan que sea seguro desreferenciar dichas variables sin comprobar primero que no se trata de un valor NULL:
  - La variable debe inicializarse como un valor distinto a NULL.
  - No se puede asignar el valor `null` a la variable.
- **Una referencia puede ser NULL**. Si las variables pueden ser NULL, el compilador aplica reglas para garantizar que haya comprobado correctamente si hay referencias NULL:
  - Solo se puede desreferenciar la variable si el compilador pueda garantizar que el valor no sea NULL.
  - Estas variables se pueden inicializar con el valor `null` predeterminado, y se les puede asignar el valor `null` en otro código.

Esta nueva característica proporciona grandes ventajas sobre el control de variables de referencia con respecto a versiones anteriores de C#, donde la intención del diseño no se puede determinar a partir de la declaración de la variable. El compilador no proporcionaba protección contra excepciones de referencia NULL para los tipos de referencia:

- **Una referencia puede ser NULL**. El compilador no emite ninguna advertencia cuando una variable de tipo de referencia se inicializa con `null` o posteriormente se le asigna `null`. El compilador emite advertencias cuando estas variables se desreferencian sin comprobaciones de valores NULL.
- **Se asume que una referencia no es NULL**. Si se desreferencian tipos de referencia, el compilador no emite ninguna advertencia. El compilador emite advertencias si una variable se establece en una expresión que puede ser NULL.

Estas advertencias se emiten en tiempo de compilación. El compilador no agrega comprobaciones de valores NULL ni otras construcciones de tiempo de ejecución en un contexto que admite un valor NULL. En tiempo de ejecución, una referencia que acepta valores NULL y una referencia que no acepta valores NULL son equivalentes.

Con la incorporación de los tipos de referencia que aceptan valores NULL, puede declarar su intención de forma más clara. El valor `null` es la forma adecuada de representar que una variable que no hace referencia a un valor. No use esta característica para eliminar todos los valores `null` de su código. En su lugar, debería declarar su intención al compilador para que los demás desarrolladores la puedan ver al leer el código. Al declarar su intención, el compilador le informa de cuándo escribe código que no es coherente con esa intención.

Un **tipo de referencia que acepta valores NULL** se anota con la misma sintaxis que los [tipos de valor que aceptan valores NULL](language-reference/builtin-types/nullable-value-types.md): se agrega `?` junto al tipo de la variable. Por ejemplo, la siguiente declaración de variable representa una variable de cadena que acepta valores NULL, `name`:

```csharp
string? name;
```

Cualquier variable en la que `?` no se anexe al nombre de tipo es un **tipo de referencia que no acepta valores NULL**. Esto incluye todas las variables de tipo de referencia en el código existente en el momento en el que se habilita esta característica.

El compilador usa el análisis estático para determinar si se sabe si una referencia que acepta valores NULL no tiene este tipo de valor. Si desreferencia una referencia que acepta valores NULL cuando esta puede ser NULL, el compilador genera una advertencia. Puede invalidar este comportamiento con el [operador de limitación de advertencias de valores NULL](language-reference/operators/null-forgiving.md)`!` después del nombre de una variable. Por ejemplo, si sabe que la variable `name` no es NULL, pero el compilador genera una advertencia, puede escribir el código siguiente para invalidar el análisis del compilador:

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a>Nulabilidad de tipos

Cualquier tipo de referencia puede tener una de cuatro *nulabilidades*, que describen cuándo se generan las advertencias:

- *No acepta valores NULL*: no se pueden asignar valores NULL a las variables de este tipo. No es necesario comprobar si estas tienen un valor NULL antes de desreferenciarlas.
- *Acepta valores NULL*: se pueden asignar valores NULL a las variables de este tipo. Si se desreferencian sin comprobar primero la existencia de valores `null`, se producirá una advertencia.
- *Inconsciente*: se trata del estado previo a C# 8.0. Las variables de este tipo se pueden desreferenciar o asignar sin advertencias.
- *Desconocido*: este es generalmente el caso de los parámetros de tipo en los que las restricciones no indican al compilador que el tipo debe *aceptar valores NULL* o *no aceptar valores NULL*.

La nulabilidad de un tipo en una declaración de variable se controla mediante el *contexto que acepta valores NULL* en el que se declara la variable.

## <a name="nullable-contexts"></a>Contextos que aceptan valores NULL

Los contextos que aceptan valores NULL permiten un control preciso sobre cómo interpreta el compilador las variables de tipos de referencia. El **contexto de anotación que acepta valores NULL** de cualquier línea de origen está habilitado o deshabilitado. Puede considerar que el compilador anterior al de C# 8.0 compilaba todo el código con el contexto que acepta valores NULL deshabilitado: cualquier tipo de referencia puede tener el valor NULL. El **contexto de advertencia que acepta valores NULL** también se puede habilitar o deshabilitar. Este contexto especifica las advertencias que genera el compilador usando el análisis de flujos.

Tanto el contexto de anotación que acepta valores NULL como el contexto de advertencia que acepta valores NULL pueden establecerse para un proyecto con el elemento `Nullable` del archivo *.csproj*. Este elemento configura la forma en la que el compilador interpreta la nulabilidad de los tipos y las advertencias que se generan. Estos son los valores válidos:

- `enable`: el contexto de anotación que acepta valores NULL es **enabled**. El contexto de advertencia que acepta valores NULL es **enabled**.
  - Las variables de un tipo de referencia, como `string`, no aceptan valores NULL.  Todas las advertencias de nulabilidad están habilitadas.
- `warnings`: el contexto de anotación que acepta valores NULL es **disabled**. El contexto de advertencia que acepta valores NULL es **enabled**.
  - Las variables de un tipo de referencia son inconscientes. Todas las advertencias de nulabilidad están habilitadas.
- `annotations`: el contexto de anotación que acepta valores NULL es **enabled**. el contexto de advertencia que acepta valores NULL es **disabled**.
  - Las variables de un tipo de referencia, como cadena, no admiten un valor NULL. Todas las advertencias de nulabilidad están deshabilitadas.
- `disable`: el contexto de anotación que acepta valores NULL es **disabled**. el contexto de advertencia que acepta valores NULL es **disabled**.
  - Las variables de tipo de referencia son inconscientes, como en versiones anteriores de C#. Todas las advertencias de nulabilidad están deshabilitadas.

**Ejemplo**:

```xml
<Nullable>enable</Nullable>
```

También puede usar directivas para establecer los mismos contextos en cualquier lugar del proyecto:

- `#nullable enable`: establece el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL en **enabled**.
- `#nullable disable`: establece el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL en **disabled**.
- `#nullable restore`: restaura el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL según la configuración del proyecto.
- `#nullable disable warnings`: establece el contexto de advertencia que acepta valores NULL en **disabled**.
- `#nullable enable warnings`: establece el contexto de advertencia que acepta valores NULL en **enabled**.
- `#nullable restore warnings`: restaura el contexto de advertencia que acepta valores NULL según la configuración del proyecto.
- `#nullable disable annotations`: establezca el contexto de anotación que admite un valor NULL en **disabled**.
- `#nullable enable annotations`: establezca el contexto de anotación que admite un valor NULL en **enabled**.
- `#nullable restore annotations`: restaura el contexto de advertencia de anotación según la configuración del proyecto.

> [!IMPORTANT]
> El contexto global que admite un valor NULL no se aplica a los archivos de código generado. En cualquier estrategia, el contexto que admite un valor NULL está *deshabilitado* para cualquier archivo de código fuente marcado como generado. Esto significa que las API de los archivos generados no se anotan. Hay cuatro maneras de marcar un archivo como generado:
>
> 1. En el archivo .editorconfig, especifique `generated_code = true` en una sección que se aplique a ese archivo.
> 1. Coloque `<auto-generated>` o `<auto-generated/>` en un comentario en la parte superior del archivo. Puede estar en cualquier línea de ese comentario, pero el bloque de comentario debe ser el primer elemento del archivo.
> 1. Inicie el nombre de archivo con *TemporaryGeneratedFile_*
> 1. Finalice el nombre de archivo con *.designer.cs*, *.generated.cs*, *.g.cs* o *.g.i.cs*.
>
> Los generadores pueden optar por usar la directiva de preprocesador [`#nullable`](language-reference/preprocessor-directives.md#nullable-context).

De forma predeterminada, los contextos de advertencias y anotaciones que aceptan valores NULL están **deshabilitados**. Esto implica que el código existente se compila sin cambios y sin generar ninguna advertencia nueva.

Estas opciones proporcionan dos estrategias distintas para [actualizar un código base existente](nullable-migration-strategies.md) para usar tipos de referencia que aceptan valores NULL.

## <a name="nullable-annotation-context"></a>Contexto de anotación que admite valores NULL

El compilador usa las siguientes reglas en un contexto de anotación deshabilitado que acepta valores NULL:

- No se pueden declarar referencias que aceptan valores NULL en un contexto deshabilitado.
- Todas las variables de referencia se pueden asignar a un valor NULL.
- No se genera ninguna advertencia al desreferenciar una variable de un tipo de referencia.
- El operador de limitación de advertencias de valores NULL no se puede usar en un contexto deshabilitado.

El comportamiento es el mismo que en versiones anteriores de C#.

El compilador usa las siguientes reglas en un contexto de anotación habilitado que acepta valores NULL:

- Todas las variables de tipo de referencia son **referencias que no aceptan valores NULL**.
- Estas referencias se pueden desreferenciar sin problemas.
- Todos los tipos de referencia que aceptan valores NULL (con la anotación de `?` después del tipo en la declaración de la variable) pueden ser NULL. El análisis estático determina si se sabe que el valor no admite valores NULL cuando se desreferencia. Si no, el compilador emite una advertencia.
- Puede usar el operador de limitación de advertencias de valores NULL para declarar que una referencia que acepta valores NULL no tiene un valor NULL.

En un contexto de anotación que acepta valores NULL, el carácter `?` junto a un tipo de referencia declara un **tipo de referencia que acepta valores NULL**. Se puede incorporar un **operador de limitación de advertencias de valores NULL**`!` junto a una expresión para declarar que no tiene un valor NULL.

## <a name="nullable-warning-context"></a>Contexto de advertencia que acepta valores NULL

El contexto de advertencia que acepta valores NULL no es igual al contexto de anotación que acepta valores NULL. Se pueden habilitar las advertencias incluso aunque las nuevas anotaciones estén deshabilitadas. El compilador usa el análisis de flujos estático para determinar el **estado NULL** de cualquier referencia. El estado NULL puede ser **no NULL** o **quizás NULL** cuando el *contexto de advertencia que acepta valores NULL* no está **deshabilitado**. Si desreferencia una referencia cuando el compilador ha determinado el estado **quizás NULL**, el compilador emite una advertencia. El estado de una referencia es **quizás NULL** a menos que el compilador pueda determinar una de estas dos condiciones:

1. Es evidente que a la variable se le ha asignado un valor distinto a NULL.
1. Se ha comprobado que la variable o la expresión no tiene un valor NULL antes de desreferenciarla.

El compilador genera advertencias cuando se desreferencia una variable o expresión que tiene un estado **quizás NULL** en un contexto de advertencia que admite valores NULL. Además, el compilador genera advertencias cuando se asigna una variable o expresión **quizás NULL** a una variable de tipo de referencia que no acepta valores NULL en un contexto de anotación que sí los acepta.

## <a name="attributes-describe-apis"></a>Atributos que describen las API

Agregue atributos a las API que proporcionen al compilador más información sobre cuándo los argumentos o valores devueltos pueden admitir o no valores NULL. Puede obtener más información sobre estos atributos en nuestro artículo de la referencia del lenguaje que trata de los [atributos que admiten valores NULL](language-reference/attributes/nullable-analysis.md). Estos atributos se agregan a las bibliotecas de .NET a través de las versiones actuales y futuras. Las API que se usan más a menudo se actualizan primero.

## <a name="known-pitfalls"></a>Problemas conocidos

Las matrices y las estructuras que contienen tipos de referencia son problemas conocidos de la característica de tipos de referencia que aceptan valores NULL.

### <a name="structs"></a>Estructuras

Una estructura que contiene tipos de referencia que no aceptan valores NULL permite asignarle `default` sin ninguna advertencia. Considere el ejemplo siguiente:

```csharp
using System;

#nullable enable

public struct Student
{
    public string FirstName;
    public string? MiddleName;
    public string LastName;
}

public static class Program
{
    public static void PrintStudent(Student student)
    {
        Console.WriteLine($"First name: {student.FirstName.ToUpper()}");
        Console.WriteLine($"Middle name: {student.MiddleName.ToUpper()}");
        Console.WriteLine($"Last name: {student.LastName.ToUpper()}");
    }

    public static void Main() => PrintStudent(default);
}
```

En el ejemplo anterior, no hay ninguna advertencia en `PrintStudent(default)` mientras que los tipos de referencia que no aceptan valores NULL `FirstName` y `LastName` son NULL.

Otro caso más común es cuando se trata de estructuras genéricas. Considere el ejemplo siguiente:

```csharp
#nullable enable

public struct Foo<T>
{
    public T Bar { get; set; }
}

public static class Program
{
    public static void Main()
    {
        string s = default(Foo<string>).Bar;
    }
}
```

En el ejemplo anterior, la propiedad `Bar` será `null` en tiempo de ejecución y se asigna a una cadena que no acepta valores NULL sin ninguna advertencia.

### <a name="arrays"></a>Matrices

Las matrices también son un problema conocido en los tipos de referencia que aceptan valores NULL. Considere el ejemplo siguiente, que no genera ninguna advertencia:

```csharp
using System;

#nullable enable

public static class Program
{
    public static void Main()
    {
        string[] values = new string[10];
        string s = values[0];
        Console.WriteLine(s.ToUpper());
    }
}
```

En el ejemplo anterior, la declaración de la matriz muestra que contiene cadenas que no aceptan valores NULL, mientras que todos sus elementos se inicializan en NULL. Después, a la variable `s` se le asigna un valor NULL (el primer elemento de la matriz). Por último, se desreferencia la variable `s`, lo que genera una excepción en tiempo de ejecución.

## <a name="see-also"></a>Vea también

- [Borrador de especificación de tipos de referencia que aceptan valores NULL](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md)
- [Tutorial de introducción a las referencias que no aceptan valores NULL](whats-new/tutorials/nullable-reference-types.md)
- [Migración de un código base existente a referencias que aceptan valores NULL](whats-new/tutorials/upgrade-to-nullable-references.md)
- [**Nullable** (opción del compilador de C#)](language-reference/compiler-options/language.md#nullable)
