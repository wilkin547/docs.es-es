---
title: -langversion (Opciones del compilador de C#)
ms.date: 08/23/2019
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 007b10f6f27233c43caad4c1910e3d1158682950
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920366"
---
# <a name="-langversion-c-compiler-options"></a>-langversion (Opciones del compilador de C#)

Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje C#.

## <a name="syntax"></a>Sintaxis

```console
-langversion:option
```

## <a name="arguments"></a>Argumentos

`option`

Valores válidos son:

|Opción|Significado|
|------------|-------------|
|preview|El compilador acepta toda la sintaxis de lenguaje válida de la última versión preliminar que puede admitir.|
|latest|El compilador acepta toda la sintaxis de lenguaje válida de la última versión (incluidas las secundarias) que puede admitir.|
|latestMajor|El compilador acepta toda la sintaxis de lenguaje válida de la última versión principal que puede admitir.|
|8.0|El compilador acepta solo la sintaxis que se incluye en C# 8.0 o versiones anteriores.|
|7.3|El compilador acepta solo la sintaxis que se incluye en C# 7.3 o versiones anteriores.|
|7.2|El compilador acepta solo la sintaxis que se incluye en C# 7.2 o versiones anteriores.|
|7.1|El compilador acepta solo la sintaxis que se incluye en C# 7.1 o versiones anteriores.|
|7|El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores.|
|6|El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores.|
|5|El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores.|
|4|El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores.|
|3|El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores.|
|ISO-2|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0).|
|ISO-1|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2).|

La versión de idioma predeterminada depende de la plataforma de destino de la aplicación y la versión del SDK o de Visual Studio instalada. Estas reglas se definen en el artículo sobre la [configuración de la versión del lenguaje](../configure-language-version.md#defaults).

## <a name="remarks"></a>Comentarios

Los metadatos a los que hace referencia la aplicación de C# no están sujetos a la opción del compilador **-langversion**.

Dado que cada versión del compilador de C# contiene las extensiones para la especificación del lenguaje, **-langversion** no ofrece las funciones equivalentes de una versión anterior del compilador.

Además, aunque las actualizaciones de versión de C# generalmente coinciden con las versiones de .NET Framework principales, la sintaxis y las características nuevas no están necesariamente asociadas a esa versión de marco específica. Aunque las nuevas características necesitan definitivamente una nueva actualización del compilador que también se publica junto con la revisión de C#, cada característica específica tiene su propia API mínima de .NET o requisitos de Common Language Runtime que pueden permitir que se ejecute en marcos de versiones anteriores mediante la inclusión de paquetes NuGet u otras bibliotecas.

Independientemente de la configuración de **-langversion** que use, usa la versión actual de Common Language Runtime para crear el archivo .exe o .dll. Una excepción son los ensamblados de confianza y [-moduleassemblyname (Opción del compilador de C#)](./moduleassemblyname-compiler-option.md), que funcionan en **-langversion:ISO-1**.

Para obtener otras formas de especificar la versión del lenguaje C#, consulte el artículo [Selección de la versión del lenguaje C#](../configure-language-version.md).

Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

|Versión|Link|Descripción|
|-------|----|-----------|
|C# 7.0 y posterior||actualmente, no disponible|
|C# 6.0|[Vínculo](/dotnet/csharp/language-reference/language-specification/introduction)|Versión 6 de la especificación del lenguaje C#, borrador no oficial: .NET Foundation|
|C# 5.0|[Descargar PDF](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|Norma ECMA-334 estándar, quinta edición|
|C# 3.0|[Decargar DOC](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|Especificación del lenguaje C#, versión 3.0: Microsoft Corporation|
|C# 2.0|[Descargar PDF](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|Norma ECMA-334 estándar, cuarta edición|
|C# 1.2|[Decargar DOC](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|Especificación del lenguaje C#, versión 1.2: Microsoft Corporation|
|C# 1.0|[Decargar DOC](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|Especificación del lenguaje C#, versión 1.0: Microsoft Corporation|

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a>Versión del SDK mínima necesaria para admitir todas las características del lenguaje

En la tabla siguiente se enumeran las versiones mínimas del SDK con el compilador de C# que admite la versión del lenguaje correspondiente:

|Versión de C#|Versión mínima del SDK|
|----------|-------------------|
|C# 8.0| Microsoft Visual Studio/Build Tools 2019, versión 16.3 o SDK de .NET Core 3.0 |
|C# 7.3| Microsoft Visual Studio/Build Tools 2017, versión 15.7 |
|C# 7.2| Microsoft Visual Studio/Build Tools 2017, versión 15.5 |
|C# 7.1| Microsoft Visual Studio/Build Tools 2017, versión 15.3 |
|C# 7.0| Microsoft Visual Studio/Build Tools 2017 |
|C# 6| Microsoft Visual Studio/Build Tools 2015 |
|C# 5| Microsoft Visual Studio/Build Tools 2012 o compilador empaquetado de .NET Framework 4.5 |
|C# 4| Microsoft Visual Studio/Build Tools 2010 o compilador empaquetado de .NET Framework 4.0 |
|C# 3| Microsoft Visual Studio/Build Tools 2008 o compilador empaquetado de .NET Framework 3.5 |
|C# 2| Microsoft Visual Studio/Build Tools 2005 o compilador empaquetado de .NET Framework 2.0 |
|C# 1.0/1.2 | Microsoft Visual Studio/Build Tools .NET 2002 o compilador empaquetado de .NET Framework 1.0 |

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
