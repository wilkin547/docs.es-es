---
title: 'Control de versiones del lenguaje C#: Guía de C#'
description: Obtenga información sobre cómo se determina la versión del lenguaje C# en función del proyecto y los motivos de esa decisión. Obtenga información sobre cómo invalidar el valor predeterminado de forma manual.
ms.custom: updateeachrelease
ms.date: 08/11/2020
ms.openlocfilehash: a06aa8812dad6f4b9a9254eef9f7c678c22af860
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634510"
---
# <a name="c-language-versioning"></a>Control de versiones del lenguaje C#

El compilador de C# más actualizado determina una versión de lenguaje predeterminada basada en los marcos o las plataformas de destino del proyecto. Visual Studio no proporciona una interfaz de usuario para cambiar el valor, pero se puede cambiar si se modifica el archivo *csproj*. La opción predeterminada garantiza que se use la versión del lenguaje más reciente compatible con el marco de trabajo de destino. Se beneficia del acceso a las características de lenguaje más recientes compatibles con el destino del proyecto. Esta opción predeterminada también garantiza que no se use un lenguaje que requiera tipos o el comportamiento en tiempo de ejecución no esté disponible en la plataforma de destino. La elección de una versión del lenguaje más reciente que la predeterminada puede provocar errores en tiempo de compilación y en tiempo de ejecución difíciles de diagnosticar.

Las reglas de este artículo se aplican al compilador ofrecido con Visual Studio 2019 o el SDK de .NET. Los compiladores de C# que forman parte de la instalación de Visual Studio 2017 o versiones anteriores del SDK de .NET Core tienen como destino C# 7.0 de forma predeterminada.

C# 8.0 solo se admite en .NET Core 3.x y versiones más recientes. Muchas de las características más recientes requieren características de biblioteca y runtime introducidas en .NET Core 3.x:

- [La implementación de interfaz predeterminada](../whats-new/csharp-8.md#default-interface-methods) requiere nuevas características en el CLR de .NET Core 3.0.
- Las [secuencias asincrónicas](../whats-new/csharp-8.md#asynchronous-streams) requieren los nuevos tipos <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.
- Los [índices y los intervalos](../whats-new/csharp-8.md#indices-and-ranges) requieren los nuevos tipos <xref:System.Index?displayProperty=nameWithType>y <xref:System.Range?displayProperty=nameWithType>.
- Los [tipos de referencia que admiten un valor NULL](../whats-new/csharp-8.md#nullable-reference-types) hacen uso de varios [atributos](attributes/nullable-analysis.md) para proporcionar mejores advertencias. Esos atributos se han agregado en .NET Core 3.0. Otras plataformas de destino no se han anotado con ninguno de estos atributos. Esto significa que es posible que las advertencias que admiten un valor NULL no reflejen con precisión los posibles problemas.

C# 9.0 solo se admite en .NET 5 y versiones más recientes.

## <a name="defaults"></a>Valores predeterminados

El compilador determina un valor predeterminado según estas reglas:

| Marco de destino | version | Versión predeterminada del lenguaje C# |
|------------------|---------|-----------------------------|
| .NET             | 5.x     | C# 9.0                      |
| .NET Core        | 3.x     | C# 8.0                      |
| .NET Core        | 2.x     | C# 7.3                      |
| .NET Standard    | 2.1     | C# 8.0                      |
| .NET Standard    | 2.0     | C# 7.3                      |
| .NET Standard    | 1.x     | C# 7.3                      |
| .NET Framework   | todo     | C# 7.3                      |

Cuando el proyecto tiene como destino un marco en versión preliminar que tenga una versión de lenguaje preliminar correspondiente, la versión de lenguaje que se usa es la que está en versión preliminar. Puede usar las características más recientes con esa versión preliminar en cualquier entorno, sin que afecte a los proyectos que tienen como destino una versión de .NET Core publicada.

> [!TIP]
> Para saber qué versión de lenguaje está usando actualmente, incluya `#error version` (con distinción de mayúsculas y minúsculas) en el código. Esto hace que el compilador genere un diagnóstico, CS8304, con un mensaje que contiene la versión del compilador que se usa y la versión del lenguaje seleccionada actualmente.

## <a name="override-a-default"></a>Invalidación de un valor predeterminado

Si debe especificar su versión de C# explícitamente, puede hacerlo de varias maneras:

- Editar manualmente el [archivo del proyecto](#edit-the-project-file).
- Establecer la versión del lenguaje [para varios proyectos en un subdirectorio](#configure-multiple-projects).
- Configurar la opción dl compilador [Reemplace la opción del compilador `-langversion`](compiler-options/langversion-compiler-option.md).

### <a name="edit-the-project-file"></a>Edición del archivo del proyecto

Puede establecer la versión del lenguaje en el archivo del proyecto. Por ejemplo, si quiere acceder explícitamente a las características en versión preliminar, agregue un elemento similar al siguiente:

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

El valor `preview` usa la versión preliminar más reciente disponible del lenguaje C# que admite el compilador.

### <a name="configure-multiple-projects"></a>Configurar varios proyectos

Para configurar varios proyectos, se puede crear un archivo **Directory.Build.props** que contenga el elemento `<LangVersion>`. Por lo general, esto se hace en el directorio de la solución. Agregue lo siguiente a un archivo **Directory.Build.props** en el directorio de la solución:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

Las compilaciones de todos los subdirectorios del directorio que contenga ese archivo usarán la sintaxis de la versión preliminar de C#. Para obtener más información, consulte el artículo [Personalizar una compilación](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Referencia de la versión del lenguaje C#

En la siguiente tabla se muestran las versiones actuales del lenguaje C#. Es posible que el compilador no entienda necesariamente todos los valores si es más antiguo. Si instala el SDK de .NET más reciente, tendrá acceso a todo lo que aparece.

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> Abra el [Símbolo del sistema para desarrolladores de Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md) y ejecute el siguiente comando para ver la lista de versiones de idioma disponibles en la máquina.
>
> ```CMD
> csc -langversion:?
> ```
>
> Al cuestionar la opción de compilación [ -langversion ](compiler-options/langversion-compiler-option.md) de este modo, se imprimirá algo similar a lo siguiente:
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0
> 9.0 (default)
> latestmajor
> preview
> latest
> ```
