---
title: 'Tipos de referencia que aceptan valores NULL: referencia de C#'
description: Información sobre los tipos de referencia que aceptan valores NULL de C# y su uso
ms.date: 04/06/2020
ms.openlocfilehash: 274a613a8381a2b7718c9025f51aadb2eb32af36
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471868"
---
# <a name="nullable-reference-types-c-reference"></a>Tipos de referencia que aceptan valores NULL (referencia de C#)

> [!NOTE]
> En este artículo se tratan los tipos de referencia que aceptan valores NULL. También puede declarar [tipos de valor que aceptan valores NULL](nullable-value-types.md).

Los tipos de referencia que aceptan valores NULL están disponibles a partir de C# 8.0, en un código que ha participado en un *contexto compatible con valores NULL* . Los tipos de referencia que aceptan valores NULL, las advertencias de análisis estático NULL y el [operador null-forgiving](../operators/null-forgiving.md) son características de lenguaje opcionales. Todas están desactivadas de forma predeterminada. Un *contexto que admite valores NULL* se controla en el nivel de proyecto mediante la configuración de compilación o en el código que usa pragmas.

 En un contexto compatible con valores NULL:

- Una variable de un tipo de referencia `T` se debe inicializar con un valor distinto de NULL y nunca puede tener asignado un valor que sea `null`.
- Una variable de un tipo de referencia `T?` se puede inicializar con `null` o asignarle `null`, pero debe comprobarse con `null` antes de desreferenciarla.
- Una variable `m` de tipo `T?` se considera que no es NULL cuando se aplica el operador null-forgiving, como en `m!`.

Las distinciones entre un tipo de referencia que no acepta valores NULL `T` y un tipo de referencia que acepta valores NULL `T?` se aplican mediante la interpretación del compilador de las reglas anteriores. Una variable de tipo `T` y una variable de tipo `T?` se representan mediante el mismo tipo .NET. En el ejemplo siguiente se declara una cadena que no acepta valores NULL y una cadena que acepta valores NULL y luego se usa el operador null-forgiving para asignar un valor a una cadena que no acepta valores NULL:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetCoreSyntax":::

Las variables `notNull` y `nullable` se ambas representan con el tipo <xref:System.String>. Dado que los tipos que no aceptan valores NULL y que aceptan valores NULL se almacenan como el mismo tipo, hay varias ubicaciones en las que no se permite el uso de un tipo de referencia que acepte valores NULL. En general, un tipo de referencia que acepta valores NULL no se puede usar como clase base o interfaz implementada. No se puede usar un tipo de referencia que acepte valores NULL en ninguna expresión de creación de objetos o de expresión de prueba de tipos. Un tipo de referencia que acepta valores NULL no puede ser el tipo de una expresión de acceso a miembros. En los siguientes ejemplos se muestran estas construcciones:

```csharp
public MyClass : System.Object? // not allowed
{
}

var nullEmpty = System.String?.Empty; // Not allowed
var maybeObject = new object?(); // Not allowed
try
{
    if (thing is string? nullableString) // not allowed
        Console.WriteLine(nullableString);
} catch (Exception? e) // Not Allowed
{
    Console.WriteLine("error");
}
```

## <a name="nullable-references-and-static-analysis"></a>Referencias que aceptan valores NULL y análisis estático

Los ejemplos de la sección anterior muestran la naturaleza de los tipos de referencia que aceptan valores NULL. Los tipos de referencia que aceptan valores NULL no son nuevos tipos de clase, sino anotaciones en tipos de referencia existentes. El compilador utiliza esas anotaciones para ayudarle a encontrar posibles errores de referencia nula en el código. No hay ninguna diferencia en tiempo de ejecución entre un tipo de referencia que no acepta valores NULL y un tipo de referencia que acepta valores NULL. El compilador no agrega ninguna comprobación de tiempo de ejecución para los tipos de referencia que no aceptan valores NULL. Las ventajas radican en el análisis en tiempo de compilación. El compilador genera advertencias que le ayudan a encontrar y corregir posibles errores nulos en el código. Declare su intención y el compilador le advierte cuando el código infringe dicha intención.

En un contexto habilitado para valores NULL, el compilador realiza un análisis estático de las variables de cualquier tipo de referencia, tanto si admiten valores NULL como si no aceptan valores NULL. El compilador realiza un seguimiento del estado NULL de cada variable de referencia como *no NULL* o *quizás NULL* . El estado predeterminado de una referencia que no acepta valores NULL es *no NULL* . El estado predeterminado de una referencia que acepta valores NULL es *quizás NULL* .

Los tipos de referencia que no aceptan valores NULL siempre deben ser seguros para desreferenciar porque su estado NULL es *no NULL* . Para aplicar esa regla, el compilador emite advertencias si un tipo de referencia que no acepta valores NULL no se inicializa en un valor no NULL. Las variables locales deben asignarse allí donde se declaran. Cada constructor debe asignar todos los campos, ya sea en el cuerpo, en un constructor llamado o con un inicializador de campo. El compilador emite advertencias si una referencia que no acepta valores NULL se asigna a una referencia cuyo estado es *quizás NULL* . Sin embargo, dado que una referencia que no acepta valores NULL es *no NULL* , no se emite ninguna advertencia cuando se desreferencian esas variables.

Los tipos de referencia que aceptan valores NULL se pueden inicializar o asignar a `null`. Por lo tanto, el análisis estático debe determinar que una variable es *no NULL* antes de desreferenciarla. Si se determina que una referencia que acepta valores NULL es *quizás NULL* , no se puede asignar a una variable de referencia que no acepte valores NULL. La consulta siguiente muestra ejemplos de estas advertencias:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetClassWithNullable":::

En el fragmento de código siguiente se muestra dónde el compilador emite advertencias al utilizar esta clase:

:::code language="csharp" source="snippets/shared/NullableReferenceTypes.cs" id="SnippetLocalWarnings":::

En los ejemplos anteriores se muestra el análisis estático del compilador para determinar el estado NULL de las variables de referencia. El compilador aplica las reglas de lenguaje a las asignaciones y comprobaciones de valores NULL para informar de su análisis.  El compilador no puede hacer suposiciones sobre la semántica de métodos o propiedades. Si llama a métodos que realizan comprobaciones de valores NULL, el compilador no puede saber que estos métodos afectan al estado NULL de una variable. Hay una serie de atributos que puede agregar a las API para informar al compilador sobre la semántica de los argumentos y los valores devueltos. Estos atributos se han aplicado a muchas API comunes de las bibliotecas de .NET Core. Por ejemplo, <xref:System.String.IsNullOrEmpty%2A> se ha actualizado y el compilador interpreta correctamente ese método como una comprobación de valores NULL. Para obtener más información sobre los atributos que se aplican al análisis estático de estado NULL, consulte el artículo sobre [atributos que aceptan valores NULL](../attributes/nullable-analysis.md).

## <a name="setting-the-nullable-context"></a>Establecimiento del contexto que acepta valores NULL

Hay dos formas de controlar el contexto que acepta valores NULL. En el nivel de proyecto, puede agregar la configuración del proyecto `<Nullable>enable</Nullable>`. En un archivo C# de código fuente único, puede agregar el pragma `#nullable enable` para habilitar el contexto que acepta valores NULL. Consulte el artículo sobre cómo [establecer una estrategia que acepte valores NULL](../../nullable-migration-strategies.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte las propuestas siguientes de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Tipos de referencia que aceptan valores null](~/_csharplang/proposals/csharp-8.0/nullable-reference-types.md)
- [Borrador de especificación de tipos de referencia que aceptan valores NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de valores que aceptan valores NULL](nullable-value-types.md)
