---
title: 'Control de versiones del lenguaje C#: Guía de C#'
description: Obtenga información sobre cómo se determina la versión del lenguaje C# en función del proyecto y los motivos de esa decisión. Obtenga información sobre cómo invalidar el valor predeterminado de forma manual.
ms.date: 02/21/2020
ms.openlocfilehash: ef7275aad7638f52ecbfca1dfbdb962ae242fb48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398236"
---
# <a name="c-language-versioning"></a>Control de versiones del lenguaje C#

El compilador de C# más actualizado determina una versión de lenguaje predeterminada basada en los marcos o las plataformas de destino del proyecto. Visual Studio no proporciona una interfaz de usuario para cambiar el valor, pero se puede cambiar si se modifica el archivo *csproj*. La opción predeterminada garantiza que se use la versión del lenguaje más reciente compatible con el marco de trabajo de destino. Se beneficia del acceso a las características de lenguaje más recientes compatibles con el destino del proyecto. Esta opción predeterminada también garantiza que no se use un lenguaje que requiera tipos o el comportamiento en tiempo de ejecución no esté disponible en la plataforma de destino. La elección de una versión del lenguaje más reciente que la predeterminada puede provocar errores en tiempo de compilación y en tiempo de ejecución difíciles de diagnosticar.

Las reglas de este artículo se aplican al compilador ofrecido con Visual Studio 2019 o al SDK de .NET Core 3.0. Los compiladores de C# que forman parte de la instalación de Visual Studio 2017 o versiones anteriores del SDK de .NET Core tienen como destino C# 7.0 de forma predeterminada.

C# 8.0 (y versiones posteriores) solo se admite en .NET Core 3.x y versiones más recientes. Muchas de las características más recientes requieren características de biblioteca y runtime introducidas en .NET Core 3.x:

- La implementación de miembro de interfaz predeterminada requiere nuevas características en el CLR de .NET Core 3.0.
- Las secuencias asincrónicas requieren los nuevos tipos <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.
- Los índices y los intervalos requieren los nuevos tipos <xref:System.Index?displayProperty=nameWithType> y <xref:System.Range?displayProperty=nameWithType>.
- Los tipos de referencia que admiten un valor NULL hacen uso de varios [atributos](../nullable-attributes.md) para proporcionar mejores advertencias. Esos atributos se han agregado en .NET Core 3.0. Otras plataformas de destino no se han anotado con ninguno de estos atributos. Esto significa que es posible que las advertencias que admiten un valor NULL no reflejen con precisión los posibles problemas.

## <a name="defaults"></a>Valores predeterminados

El compilador determina un valor predeterminado según estas reglas:

|Marco de destino|version|Versión predeterminada del lenguaje C#|
|----------------|-------|---------------------------|
|.NET Core|3.x|C# 8.0|
|.NET Core|2.x|C# 7.3|
|.NET Standard|2.1|C# 8.0|
|.NET Standard|2.0|C# 7.3|
|.NET Standard|1.x|C# 7.3|
|.NET Framework|todo|C# 7.3|

Cuando el proyecto tiene como destino un marco en versión preliminar que tenga una versión de lenguaje preliminar correspondiente, la versión de lenguaje que se usa es la que está en versión preliminar. Puede usar las características más recientes con esa versión preliminar en cualquier entorno, sin que afecte a los proyectos que tienen como destino una versión de .NET Core publicada.

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

En la siguiente tabla se muestran las versiones actuales del lenguaje C#. Es posible que el compilador no entienda necesariamente todos los valores si es más antiguo. Si instala .NET Core 3.0 o posterior, tiene acceso a todo lo que aparece.

|Valor|Significado|
|------------|-------------|
|preview|El compilador acepta toda la sintaxis de lenguaje válida de la última versión preliminar.|
|latest|El compilador acepta la sintaxis de la última versión del compilador (incluida las versión secundaria).|
|latestMajor|El compilador acepta la sintaxis de la versión principal más reciente del compilador.|
|8.0|El compilador acepta solo la sintaxis que se incluye en C# 8.0 o versiones anteriores.|
|7.3|El compilador acepta solo la sintaxis que se incluye en C# 7.3 o versiones anteriores.|
|7.2|El compilador acepta solo la sintaxis que se incluye en C# 7.2 o versiones anteriores.|
|7.1|El compilador acepta solo la sintaxis que se incluye en C# 7.1 o versiones anteriores.|
|7|El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores.|
|6|El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores.|
|5|El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores.|
|4|El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores.|
|3|El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores.|
|ISO-2|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0). |
|ISO-1|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2). |
