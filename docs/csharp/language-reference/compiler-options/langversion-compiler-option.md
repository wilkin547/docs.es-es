---
title: -langversion (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d3d59f63102ccf3c1d54e4028635c8daad56164
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="langversion-c-compiler-options"></a>/langversion (Opciones del compilador de C#)
Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje C#.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/langversion:option  
```  
  
## <a name="arguments"></a>Argumentos  
 `option`  
 Valores válidos son:  
  
|Opción|Significado|  
|------------|-------------|  
|default|El compilador acepta toda la sintaxis de lenguaje válida que puede admitir. <sup id="TDefault">[Valor predeterminado](#FDefault)</sup>| 
|ISO-1|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores <sup id="TCS7">[CS7](#FCS7)</sup>|
|latest|El compilador acepta toda la sintaxis de lenguaje válida que puede admitir. <sup id="TLatest">[Más reciente](#FLatest)</sup>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a>Comentarios  
 Los metadatos a los que hace referencia la aplicación de C# no están sujetos a la opción del compilador **/langversion**.  
  
 Dado que cada versión del compilador de C# contiene las extensiones para la especificación del lenguaje, **/langversion** no ofrece la funcionalidad equivalente de una versión anterior del compilador.  
 
 Además, aunque las actualizaciones de versión de C# generalmente coinciden con las versiones de .NET Framework principales, la sintaxis y las características nuevas no están necesariamente asociadas a esa versión de marco específica. Aunque las nuevas características necesitarán definitivamente una nueva actualización del compilador que también se publicará junto con la revisión de C#, cada característica específica tiene su propia API mínima de .NET o requisitos de Common Language Runtime que pueden permitir que se ejecute en marcos de versiones anteriores al incluir paquetes de NuGet u otras bibliotecas.
  
 Independientemente de la configuración de **/langversion** que use, usará la versión actual de Common Language Runtime para crear el archivo .exe o .dll. Una excepción son los ensamblados de confianza y [/moduleassemblyname (Opción del compilador de C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), que funcionan en **/langversion:ISO-1**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **Versión de lenguaje**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
    
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a>Especificación del lenguaje C#
 [Referencia de especificación del lenguaje C#](../../../csharp/language-reference/language-specification/index.md): .NET Foundation  
 C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html), tecnologías de la información, especificación del lenguaje C# Language: catálogo ISO  
 C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html), tecnologías de la información, especificación del lenguaje C# Language: catálogo ISO  
 C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 en formato PDF: normas ISO disponibles gratis  
 C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc), versión 3.0 de la especificación del lenguaje C#: Microsoft Corporation  
 C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf), norma ECMA-334, cuarta edición    
 C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029), versión 5.0 de la especificación del lenguaje C#: Microsoft Corporation  
 C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md), versión 6 de la especificación del lenguaje de C#, borrador no oficial: .NET Foundation  
 C# 7.0 (actualmente, no disponible)  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Versión del compilador mínima necesaria para admitir todas las características del lenguaje   
[↩](#TDefault)<a name="FDefault">Valor predeterminado</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 o compilador empaquetado de .NET Framework 1.0     
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 o compilador empaquetado de .NET Framework 2.0    
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 o compilador empaquetado de .NET Framework 3.5    
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 o compilador empaquetado de .NET Framework 4.0    
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 o compilador empaquetado de .NET Framework 4.5    
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015    
[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Más reciente</a>: Microsoft Visual Studio/Build Tools 2017   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
