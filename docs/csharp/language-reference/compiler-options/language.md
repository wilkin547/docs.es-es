---
description: Opciones del compilador de C# para las reglas de características del lenguaje. Estas opciones controlan cómo el compilador interpreta determinadas construcciones del lenguaje.
title: 'Opciones del compilador de C#: reglas de características del lenguaje'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- CheckForOverflowUnderflow compiler option [C#]
- AllowUnsafeBlocks compiler option [C#]
- DefineConstants compiler option [C#]
- LangVersion compiler option [C#]
- Nullable compiler option [C#]
ms.openlocfilehash: 7d1d00a52bd2ca1608d4059d7d217e763defa7b9
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482480"
---
# <a name="c-compiler-options-for-language-feature-rules"></a>Opciones del compilador de C# para las reglas de características del lenguaje

Las opciones siguientes controlan cómo el compilador interpreta las características del lenguaje. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **CheckForOverflowUnderflow** / `-checked`: se generan comprobaciones de desbordamiento.
- **AllowUnsafeBlocks** / `-unsafe`: se permite código "no seguro".
- **DefineConstants** / `-define`: se definen símbolos de compilación condicional.
- **LangVersion** / `-langversion`: se especifica la versión del lenguaje como `default` (versión principal más reciente) o `latest` (versión más reciente, incluidas las versiones secundarias).
- **Nullable** / `-nullable`: se habilita el contexto que admite un valor NULL o advertencias que admiten un valor NULL.

## <a name="checkforoverflowunderflow"></a>CheckForOverflowUnderflow

La opción **CheckForOverflowUnderflow** especifica si una instrucción aritmética de enteros que produce un valor fuera del intervalo del tipo de datos genera una excepción en tiempo de ejecución.  

```xml
<CheckForOverflowUnderflow>true</CheckForOverflowUnderflow>
```

Una instrucción aritmética de enteros que está en el ámbito de una palabra clave `checked` o `unchecked` no está sujeta al efecto de la opción **CheckForOverflowUnderflow**. Si una instrucción aritmética de enteros que no está en el ámbito de una palabra clave `checked` o `unchecked` produce un valor fuera del intervalo del tipo de datos, y **CheckForOverflowUnderflow** es `true`, esa instrucción inicia una excepción en tiempo de ejecución. Si **CheckForOverflowUnderflow** es `false`, esa instrucción inicia una excepción en tiempo de ejecución. El valor predeterminado para esta opción es `false` y la comprobación de desbordamiento está deshabilitada.

## <a name="allowunsafeblocks"></a>AllowUnsafeBlocks

La opción del compilador **AllowUnsafeBlocks** permite la compilación de código en el que se usa la palabra clave [unsafe](../keywords/unsafe.md). El valor predeterminado de esta opción es `false`, lo que significa que no se permite el código no seguro.

```xml
<AllowUnsafeBlocks>true</AllowUnsafeBlocks>
```

Para obtener más información sobre el código no seguro, vea [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md).

## <a name="defineconstants"></a>DefineConstants

La opción **DefineConstants** define símbolos en todos los archivos de código fuente del programa.

```xml
<DefineConstants>name;name2</DefineConstants>
```

Esta opción especifica los nombres de uno o más símbolos que quiera definir. La opción **DefineConstants** tiene el mismo efecto que la directiva del preprocesador [#define](../preprocessor-directives/preprocessor-define.md), salvo que la opción del compilador está en vigor para todos los archivos del proyecto. Un símbolo permanece definido en un archivo de origen hasta que una directiva [#undef](../preprocessor-directives/preprocessor-undef.md) en el archivo de origen quita la definición. Cuando usa la opción `-define`, una directiva `#undef` en un archivo no tiene ningún efecto en otros archivos de código fuente del proyecto. Los símbolos creados por esta opción se pueden usar con [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md) y [#endif](../preprocessor-directives/preprocessor-endif.md) para compilar los archivos de origen condicionalmente. El propio compilador de C# no define ningún símbolo o macro que puede usar en su código fuente; todas las definiciones de símbolo deben definirse por el usuario.

> [!NOTE]
> El valor de la directiva `#define` de C# no permite que se le proporcione un valor a un símbolo, como sucede en lenguajes como C++. Por ejemplo, `#define` no puede usarse para crear una macro o para definir una constante. Si necesita definir una constante, use una variable `enum`. Si quiere crear una macro de estilo de C++, considere alternativas como genéricos. Como las macros son notoriamente propensas a errores, C# deshabilita su uso pero proporciona alternativas más seguras.

## <a name="langversion"></a>LangVersion

Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje C#.

```xml
<LangVersion>9.0</LangVersion>
```

Valores válidos son:

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

La versión de idioma predeterminada depende de la plataforma de destino de la aplicación y la versión del SDK o de Visual Studio instalada. Esas reglas se definen en el [control de versiones del lenguaje C#](../configure-language-version.md#defaults).

Los metadatos a los que hace referencia la aplicación de C# no están sujetos a la opción del compilador **LangVersion**.

Como cada versión del compilador de C# contiene extensiones para la especificación del lenguaje, **LangVersion** no ofrece las funciones equivalentes de una versión anterior del compilador.

Además, aunque las actualizaciones de versión de C# generalmente coinciden con las versiones principales de .NET Framework, la sintaxis y las características nuevas no están necesariamente asociadas a esa versión de marco específica. Aunque las nuevas características necesitan definitivamente una nueva actualización del compilador que también se publica junto con la revisión de C#, cada característica específica tiene su propia API mínima de .NET o requisitos de Common Language Runtime que pueden permitir que se ejecute en marcos de versiones anteriores mediante la inclusión de paquetes NuGet u otras bibliotecas.

Independientemente de la configuración de **LangVersion** que utilice, use la versión actual de Common Language Runtime para crear el archivo .exe o .dll. Una excepción son los ensamblados de confianza y [**ModuleAssemblyName**](advanced.md#moduleassemblyname), que funcionan en **-langversion:ISO-1**.

Para obtener otras formas de especificar la versión del lenguaje C#, vea [Control de versiones del lenguaje C#](../configure-language-version.md).

Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.

### <a name="c-language-specification"></a>Especificación del lenguaje C#

| Versión          | Link                       | Descripción                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| C# 7.0 y posterior |                            | No está disponible actualmente                                                 |
| C# 6.0           | [Vínculo][csharp-6]           | Versión 6 de la especificación del lenguaje C#, borrador no oficial: .NET Foundation |
| C# 5.0           | [Descargar PDF][csharp-5]   | Norma ECMA-334 estándar, quinta edición                                           |
| C# 3.0           | [Decargar DOC][csharp-3]   | Especificación del lenguaje C#, versión 3.0: Microsoft Corporation            |
| C# 2.0           | [Descargar PDF][csharp-2]   | Norma ECMA-334 estándar, cuarta edición                                           |
| C# 1.2           | [Decargar DOC][csharp-1.2] | Especificación del lenguaje C#, versión 1.2: Microsoft Corporation            |
| C# 1.0           | [Decargar DOC][csharp-1]   | Especificación del lenguaje C#, versión 1.0: Microsoft Corporation            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

### <a name="minimum-sdk-version-needed-to-support-all-language-features"></a>Versión del SDK mínima necesaria para admitir todas las características del lenguaje

En la tabla siguiente se enumeran las versiones mínimas del SDK con el compilador de C# que admite la versión del lenguaje correspondiente:

| Versión de C# | Versión mínima del SDK                                                                  |
|------------|--------------------------------------------------------------------------------------|
| C# 8.0     | Microsoft Visual Studio/Build Tools 2019, versión 16.3 o SDK de .NET Core 3.0         |
| C# 7.3     | Microsoft Visual Studio/Build Tools 2017, versión 15.7                               |
| C# 7.2     | Microsoft Visual Studio/Build Tools 2017, versión 15.5                               |
| C# 7.1     | Microsoft Visual Studio/Build Tools 2017, versión 15.3                               |
| C# 7.0     | Microsoft Visual Studio/Build Tools 2017                                             |
| C# 6       | Microsoft Visual Studio/Build Tools 2015                                             |
| C# 5       | Microsoft Visual Studio/Build Tools 2012 o compilador empaquetado de .NET Framework 4.5      |
| C# 4       | Microsoft Visual Studio/Build Tools 2010 o compilador empaquetado de .NET Framework 4.0      |
| C# 3       | Microsoft Visual Studio/Build Tools 2008 o compilador empaquetado de .NET Framework 3.5      |
| C# 2       | Microsoft Visual Studio/Build Tools 2005 o compilador empaquetado de .NET Framework 2.0      |
| C# 1.0/1.2 | Microsoft Visual Studio/Build Tools .NET 2002 o compilador empaquetado de .NET Framework 1.0 |

## <a name="nullable"></a>Nullable

La opción **Nullable** le permite especificar el contexto que admite un valor NULL.

```xml
<Nullable>enable</Nullable>
```

El argumento debe ser uno de `enable`, `disable`, `warnings` o `annotations`. El argumento `enable` habilita el contexto que admite un valor NULL. Si se especifica `disable`, se deshabilitará el contexto que admite un valor NULL. Al proporcionar el argumento `warnings`, se habilita el contexto de advertencia que admite un valor NULL. Al especificar el argumento `annotations`, se habilita el contexto de anotación que admite un valor NULL.

El análisis de flujo se utiliza para inferir la nulabilidad de las variables del código ejecutable. La nulabilidad inferida de una variable es independiente de la nulabilidad declarada de dicha variable. Las llamadas de método se analizan incluso cuando se omiten de forma condicional. Es el caso de <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> en modo de versión.

La invocación de métodos anotados con los siguientes atributos también afectará al análisis de flujo:

- Condiciones previas simples: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute>
- Condiciones posteriores simples: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute>
- Condiciones posteriores condicionales: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> y <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute>
- <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (por ejemplo, `DoesNotReturnIf(false)` para <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) y <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- Condiciones posteriores de miembros: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> y <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])>

> [!IMPORTANT]
> El contexto global que admite un valor NULL no se aplica a los archivos de código generado. Con independencia de este valor, el contexto que admite un valor NULL está *deshabilitado* para cualquier archivo de código fuente marcado como generado. Hay cuatro maneras de marcar un archivo como generado:
>
> 1. En el archivo .editorconfig, especifique `generated_code = true` en una sección que se aplique a ese archivo.
> 1. Coloque `<auto-generated>` o `<auto-generated/>` en un comentario en la parte superior del archivo. Puede estar en cualquier línea de ese comentario, pero el bloque de comentario debe ser el primer elemento del archivo.
> 1. Inicie el nombre de archivo con *TemporaryGeneratedFile_*
> 1. Finalice el nombre de archivo con *.designer.cs*, *.generated.cs*, *.g.cs* o *.g.i.cs*.
>
> Los generadores pueden optar por usar la directiva de preprocesador [`#nullable`](../preprocessor-directives/preprocessor-nullable.md).
