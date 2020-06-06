---
title: <compiler> (Elemento)
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 46676f25597f85596598d6f67c98930971cb0447
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088058"
---
# <a name="compiler-element"></a><span data-ttu-id="4bf90-102">\<compiler> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="4bf90-102">\<compiler> Element</span></span>

<span data-ttu-id="4bf90-103">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4bf90-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**

## <a name="syntax"></a><span data-ttu-id="4bf90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bf90-104">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4bf90-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4bf90-105">Attributes and Elements</span></span>

<span data-ttu-id="4bf90-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4bf90-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4bf90-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4bf90-107">Attributes</span></span>

|<span data-ttu-id="4bf90-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="4bf90-108">Attribute</span></span>|<span data-ttu-id="4bf90-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bf90-109">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="4bf90-110">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="4bf90-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4bf90-111">Especifica argumentos adicionales específicos del compilador para la compilación.</span><span class="sxs-lookup"><span data-stu-id="4bf90-111">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="4bf90-112">Los valores del `compilerOptions` atributo se enumeran normalmente en un tema de opciones del compilador para el compilador.</span><span class="sxs-lookup"><span data-stu-id="4bf90-112">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="4bf90-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4bf90-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4bf90-114">Proporciona una lista separada por puntos y comas de extensiones de nombre de archivo usadas por los archivos de código fuente para el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4bf90-114">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="4bf90-115">Por ejemplo, ".cs".</span><span class="sxs-lookup"><span data-stu-id="4bf90-115">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="4bf90-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4bf90-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="4bf90-117">Proporciona una lista separada por puntos y comas de nombres de idioma admitidos por el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4bf90-117">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="4bf90-118">Por ejemplo, "C#;cs;csharp".</span><span class="sxs-lookup"><span data-stu-id="4bf90-118">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="4bf90-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4bf90-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="4bf90-120">Especifica el nombre de tipo del proveedor de lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor.</span><span class="sxs-lookup"><span data-stu-id="4bf90-120">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="4bf90-121">El nombre de tipo debe cumplir los requisitos definidos en la [especificación de nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="4bf90-121">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="4bf90-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="4bf90-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4bf90-123">Especifica el nivel de advertencia del compilador predeterminado; determina el nivel en el que el proveedor de lenguaje trata las advertencias de compilación como errores.</span><span class="sxs-lookup"><span data-stu-id="4bf90-123">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4bf90-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4bf90-124">Child Elements</span></span>

|<span data-ttu-id="4bf90-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bf90-125">Element</span></span>|<span data-ttu-id="4bf90-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bf90-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4bf90-127">\<providerOption>Element</span><span class="sxs-lookup"><span data-stu-id="4bf90-127">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="4bf90-128">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4bf90-128">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4bf90-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4bf90-129">Parent Elements</span></span>

|<span data-ttu-id="4bf90-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bf90-130">Element</span></span>|<span data-ttu-id="4bf90-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bf90-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4bf90-132">\<configuration>Element</span><span class="sxs-lookup"><span data-stu-id="4bf90-132">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="4bf90-133">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4bf90-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="4bf90-134">\<system.codedom>Element</span><span class="sxs-lookup"><span data-stu-id="4bf90-134">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="4bf90-135">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="4bf90-135">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="4bf90-136">\<compilers>Element</span><span class="sxs-lookup"><span data-stu-id="4bf90-136">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="4bf90-137">Contenedor para los elementos de configuración del compilador; contiene cero o más `<compiler>` elementos.</span><span class="sxs-lookup"><span data-stu-id="4bf90-137">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4bf90-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4bf90-138">Remarks</span></span>

<span data-ttu-id="4bf90-139">Cada `<compiler>` elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="4bf90-139">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="4bf90-140">El proveedor extiende la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> clase para un lenguaje específico; el `<compiler>` elemento define la configuración del compilador y del generador de código para el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4bf90-140">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="4bf90-141">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4bf90-141">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="4bf90-142">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="4bf90-142">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="4bf90-143">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="4bf90-143">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="4bf90-144">Los elementos del compilador de la aplicación o el archivo de configuración Web pueden complementar o invalidar la configuración del archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="4bf90-144">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="4bf90-145">Si se configura más de una implementación de proveedor para el mismo nombre de idioma o la misma extensión de archivo, la última configuración coincidente invalida todos los proveedores configurados anteriormente para ese nombre de idioma o extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="4bf90-145">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="4bf90-146">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4bf90-146">Configuration File</span></span>

<span data-ttu-id="4bf90-147">Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bf90-147">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="4bf90-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bf90-148">Example</span></span>

<span data-ttu-id="4bf90-149">En el ejemplo siguiente se muestra un elemento de configuración de compilador típico:</span><span class="sxs-lookup"><span data-stu-id="4bf90-149">The following example illustrates a typical compiler configuration element:</span></span>

```xml
<configuration>
  <system.codedom>
    <compilers>
      <!-- zero or more compiler elements -->
      <compiler
        language="c#;cs;csharp"
        extension=".cs"
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"
        compilerOptions="/optimize"
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="4bf90-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bf90-150">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="4bf90-151">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4bf90-151">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4bf90-152">\<compilers>Element</span><span class="sxs-lookup"><span data-stu-id="4bf90-152">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="4bf90-153">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="4bf90-153">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="4bf90-154">[Elemento compiler aplicado a compilers para compilation (Esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4bf90-154">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
