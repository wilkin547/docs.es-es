---
title: -langversion (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f1088221a96d0176f08b4c01044e20ab6238fc13
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="ad9ba-102">-langversion (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ad9ba-102">-langversion (C# Compiler Options)</span></span>
<span data-ttu-id="ad9ba-103">Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad9ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad9ba-104">Syntax</span></span>  
  
```console  
-langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad9ba-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad9ba-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="ad9ba-106">Valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="ad9ba-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="ad9ba-107">Opción</span><span class="sxs-lookup"><span data-stu-id="ad9ba-107">Option</span></span>|<span data-ttu-id="ad9ba-108">Significado</span><span class="sxs-lookup"><span data-stu-id="ad9ba-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="ad9ba-109">default</span><span class="sxs-lookup"><span data-stu-id="ad9ba-109">default</span></span>|<span data-ttu-id="ad9ba-110">El compilador acepta toda la sintaxis de lenguaje válida de la última versión principal que puede admitir.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-110">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span> <span data-ttu-id="ad9ba-111"><sup id="TDefault">[Valor predeterminado](#FDefault)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-111"><sup id="TDefault">[Default](#FDefault)</sup></span></span>| 
|<span data-ttu-id="ad9ba-112">ISO-1</span><span class="sxs-lookup"><span data-stu-id="ad9ba-112">ISO-1</span></span>|<span data-ttu-id="ad9ba-113">El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-113">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="ad9ba-114">ISO-2</span><span class="sxs-lookup"><span data-stu-id="ad9ba-114">ISO-2</span></span>|<span data-ttu-id="ad9ba-115">El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-115">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="ad9ba-116">3</span><span class="sxs-lookup"><span data-stu-id="ad9ba-116">3</span></span>|<span data-ttu-id="ad9ba-117">El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-117">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="ad9ba-118">4</span><span class="sxs-lookup"><span data-stu-id="ad9ba-118">4</span></span>|<span data-ttu-id="ad9ba-119">El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-119">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="ad9ba-120">5</span><span class="sxs-lookup"><span data-stu-id="ad9ba-120">5</span></span>|<span data-ttu-id="ad9ba-121">El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-121">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="ad9ba-122">6</span><span class="sxs-lookup"><span data-stu-id="ad9ba-122">6</span></span>|<span data-ttu-id="ad9ba-123">El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-123">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="ad9ba-124">7</span><span class="sxs-lookup"><span data-stu-id="ad9ba-124">7</span></span>|<span data-ttu-id="ad9ba-125">El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-125">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="ad9ba-126">latest</span><span class="sxs-lookup"><span data-stu-id="ad9ba-126">latest</span></span>|<span data-ttu-id="ad9ba-127">El compilador acepta toda la sintaxis de lenguaje válida que puede admitir.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-127">The compiler accepts all valid language syntax that it can support.</span></span> <span data-ttu-id="ad9ba-128"><sup id="TLatest">[Más reciente](#FLatest)</sup></span><span class="sxs-lookup"><span data-stu-id="ad9ba-128"><sup id="TLatest">[Latest](#FLatest)</sup></span></span>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="ad9ba-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad9ba-129">Remarks</span></span>  
 <span data-ttu-id="ad9ba-130">Los metadatos a los que hace referencia la aplicación de C# no están sujetos a la opción del compilador **-langversion**.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-130">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>  
  
 <span data-ttu-id="ad9ba-131">Dado que cada versión del compilador de C# contiene las extensiones para la especificación del lenguaje, **-langversion** no ofrece las funciones equivalentes de una versión anterior del compilador.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-131">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="ad9ba-132">Además, aunque las actualizaciones de versión de C# generalmente coinciden con las versiones de .NET Framework principales, la sintaxis y las características nuevas no están necesariamente asociadas a esa versión de marco específica.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-132">Additionally, while C# version updates generally coincide with major .Net Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="ad9ba-133">Aunque las nuevas características necesitarán definitivamente una nueva actualización del compilador que también se publicará junto con la revisión de C#, cada característica específica tiene su propia API mínima de .NET o requisitos de Common Language Runtime que pueden permitir que se ejecute en marcos de versiones anteriores al incluir paquetes de NuGet u otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-133">While the new features will definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .Net API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="ad9ba-134">Independientemente de la configuración de **-langversion** que use, usará la versión actual de Common Language Runtime para crear el archivo .exe o .dll.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-134">Regardless of which **-langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="ad9ba-135">Una excepción son los ensamblados de confianza y [-moduleassemblyname (Opción del compilador de C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), que funcionan en **-langversion:ISO-1**.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-135">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ad9ba-136">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ad9ba-136">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ad9ba-137">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-137">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="ad9ba-138">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-138">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="ad9ba-139">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="ad9ba-139">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="ad9ba-140">Modifique la propiedad **Versión de lenguaje**.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-140">Modify the **Language Version** property.</span></span>  
  
 <span data-ttu-id="ad9ba-141">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad9ba-141">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="ad9ba-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad9ba-142">See Also</span></span>  
 [<span data-ttu-id="ad9ba-143">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="ad9ba-143">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="ad9ba-144">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="ad9ba-144">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="ad9ba-145">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ad9ba-145">C# Language Specification</span></span>
 <span data-ttu-id="ad9ba-146">[Referencia de especificación del lenguaje C#](../../../csharp/language-reference/language-specification/index.md): .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="ad9ba-146">[C# Language Specification Reference](../../../csharp/language-reference/language-specification/index.md) : .NET Foundation</span></span>  
 <span data-ttu-id="ad9ba-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html), tecnologías de la información, especificación del lenguaje C# Language: catálogo ISO</span><span class="sxs-lookup"><span data-stu-id="ad9ba-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="ad9ba-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html), tecnologías de la información, especificación del lenguaje C# Language: catálogo ISO</span><span class="sxs-lookup"><span data-stu-id="ad9ba-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="ad9ba-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 en formato PDF: normas ISO disponibles gratis</span><span class="sxs-lookup"><span data-stu-id="ad9ba-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 in PDF format : ISO Freely Available Standards</span></span>  
 <span data-ttu-id="ad9ba-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc), versión 3.0 de la especificación del lenguaje C#: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="ad9ba-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# Language Specification Version 3.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="ad9ba-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf), norma ECMA-334, cuarta edición</span><span class="sxs-lookup"><span data-stu-id="ad9ba-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334 4th Edition</span></span>    
 <span data-ttu-id="ad9ba-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029), versión 5.0 de la especificación del lenguaje C#: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="ad9ba-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# Language Specification Version 5.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="ad9ba-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md), versión 6 de la especificación del lenguaje de C#, borrador no oficial: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="ad9ba-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# Language Specification Version 6 - Unofficial Draft : .NET Foundation</span></span>  
 <span data-ttu-id="ad9ba-154">C# 7.0 (actualmente, no disponible)</span><span class="sxs-lookup"><span data-stu-id="ad9ba-154">C# 7.0 (not currently available)</span></span>  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="ad9ba-155">Versión del compilador mínima necesaria para admitir todas las características del lenguaje</span><span class="sxs-lookup"><span data-stu-id="ad9ba-155">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="ad9ba-156">[↩](#TDefault)<a name="FDefault">Valor predeterminado</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 o compilador empaquetado de .NET Framework 1.0</span><span class="sxs-lookup"><span data-stu-id="ad9ba-156">[↩](#TDefault)<a name="FDefault">Default</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="ad9ba-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 o compilador empaquetado de .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="ad9ba-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="ad9ba-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 o compilador empaquetado de .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="ad9ba-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="ad9ba-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 o compilador empaquetado de .NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="ad9ba-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="ad9ba-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 o compilador empaquetado de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ad9ba-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="ad9ba-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="ad9ba-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="ad9ba-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Más reciente</a>: Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="ad9ba-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
