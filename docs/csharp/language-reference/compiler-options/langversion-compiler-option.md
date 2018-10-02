---
title: -langversion (Opciones del compilador de C#)
ms.date: 05/14/2018
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 9ebc90b3d4f610aec58f950f375d97fd2abf3617
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857276"
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
|default|El compilador acepta toda la sintaxis de lenguaje válida de la última versión principal que puede admitir.|
|ISO-1|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores <sup id="TCS7">[CS7](#FCS7)</sup>|
|7.1|El compilador acepta solo la sintaxis que se incluye en C# 7.1 o versiones anteriores <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|El compilador acepta solo la sintaxis que se incluye en C# 7.2 o versiones anteriores <sup id="TCS72">[CS72](#FCS72)</sup>|
|7.3|El compilador acepta solo la sintaxis que se incluye en C# 7.3 o versiones anteriores <sup id="TCS73">[CS73](#FCS73)</sup>|
|latest|El compilador acepta toda la sintaxis de lenguaje válida que puede admitir.|

<!--- Uncomment and move these above
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS8">[CS8](#FCS8)</sup>|
-->

## <a name="remarks"></a>Comentarios

 Los metadatos a los que hace referencia la aplicación de C# no están sujetos a la opción del compilador **-langversion**.  
  
 Dado que cada versión del compilador de C# contiene las extensiones para la especificación del lenguaje, **-langversion** no ofrece las funciones equivalentes de una versión anterior del compilador.  

 Además, aunque las actualizaciones de versión de C# generalmente coinciden con las versiones de .NET Framework principales, la sintaxis y las características nuevas no están necesariamente asociadas a esa versión de marco específica. Aunque las nuevas características necesitan definitivamente una nueva actualización del compilador que también se publica junto con la revisión de C#, cada característica específica tiene su propia API mínima de .NET o requisitos de Common Language Runtime que pueden permitir que se ejecute en marcos de versiones anteriores mediante la inclusión de paquetes NuGet u otras bibliotecas.
  
 Independientemente de la configuración de **-langversion** que use, usará la versión actual de Common Language Runtime para crear el archivo .exe o .dll. Una excepción son los ensamblados de confianza y [-moduleassemblyname (Opción del compilador de C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), que funcionan en **-langversion:ISO-1**.  

 Para obtener otras formas de especificar la versión del lenguaje C#, vea el tema [Select the C# language version](../configure-language-version.md) (Selección de la versión del lenguaje C#).
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](index.md)  
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  

### <a name="c-language-specification"></a>Especificación del lenguaje C#

|Versión|Vínculo|Descripción|
|-------|----|-----------|
|C# 1.0|[Decargar DOC](https://download.microsoft.com/download/a/9/e/a9e229b9-fee5-4c3e-8476-917dee385062/csharp%20language%20specification%20v1.0.doc)|Versión 1.0 de la especificación del lenguaje C#: Microsoft Corporation|
|C# 1.2|[Decargar DOC](https://download.microsoft.com/download/5/e/5/5e58be0a-b02b-41ac-a4a3-7a22286214ff/csharp%20language%20specification%20v1.2.doc)|Versión 1.2 de la especificación del lenguaje C#: Microsoft Corporation|
|C# 2.0|[Descargar PDF](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/Ecma-334%204th%20edition%20June%202006.pdf)|Norma ECMA-334 estándar, cuarta edición|
|C# 3.0|[Decargar DOC](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|Versión 3.0 de la especificación del lenguaje C#: Microsoft Corporation|
|C# 5.0|[Descargar PDF](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf)|Norma ECMA-334 estándar, quinta edición|
|C# 6.0|[Vínculo](../language-specification/index.md)|Versión 6 de la especificación del lenguaje C#, borrador no oficial: .NET Foundation|
|C# 7.0 y posterior||actualmente, no disponible|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Versión del compilador mínima necesaria para admitir todas las características del lenguaje

[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 o compilador empaquetado de .Net Framework 1.0 [↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 o compilador empaquetado de .Net Framework 2.0 [↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 o compilador empaquetado de .Net Framework 3.5 [↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 o compilador empaquetado de .Net Framework 4.0 [↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 o compilador empaquetado de .Net Framework 4.5 [↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015 [↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017 [↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, versión 15.3 [↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, versión 15.5 [↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, versión 15.7

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS8)<a name="FCS8">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
