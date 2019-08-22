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
ms.openlocfilehash: 80eea3373e2f4b7e45ebeb31dd6552ea02c109e1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659729"
---
# <a name="compiler-element"></a><span data-ttu-id="e2ec0-102">\<Elemento > del compilador</span><span class="sxs-lookup"><span data-stu-id="e2ec0-102">\<compiler> Element</span></span>

<span data-ttu-id="e2ec0-103">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="e2ec0-104">\<elemento de configuración \<> elemento System. CodeDom \<> elemento compiladores \<> elemento > del compilador</span><span class="sxs-lookup"><span data-stu-id="e2ec0-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="e2ec0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2ec0-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e2ec0-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e2ec0-106">Attributes and Elements</span></span>

<span data-ttu-id="e2ec0-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e2ec0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2ec0-108">Attributes</span></span>

|<span data-ttu-id="e2ec0-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2ec0-109">Attribute</span></span>|<span data-ttu-id="e2ec0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2ec0-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="e2ec0-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e2ec0-112">Especifica argumentos adicionales específicos del compilador para la compilación.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="e2ec0-113">Los valores `compilerOptions` del atributo se enumeran normalmente en un tema de opciones del compilador para el compilador.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="e2ec0-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2ec0-115">Proporciona una lista separada por puntos y comas de extensiones de nombre de archivo usadas por los archivos de código fuente para el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="e2ec0-116">Por ejemplo, ". cs".</span><span class="sxs-lookup"><span data-stu-id="e2ec0-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="e2ec0-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2ec0-118">Proporciona una lista separada por puntos y comas de nombres de idioma admitidos por el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="e2ec0-119">Por ejemplo, "c#; CS; CSharp".</span><span class="sxs-lookup"><span data-stu-id="e2ec0-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="e2ec0-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2ec0-121">Especifica el nombre de tipo del proveedor de lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="e2ec0-122">El nombre de tipo debe cumplir los requisitos definidos en la [especificación de nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e2ec0-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="e2ec0-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e2ec0-124">Especifica el nivel de advertencia del compilador predeterminado; determina el nivel en el que el proveedor de lenguaje trata las advertencias de compilación como errores.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e2ec0-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e2ec0-125">Child Elements</span></span>

|<span data-ttu-id="e2ec0-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2ec0-126">Element</span></span>|<span data-ttu-id="e2ec0-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2ec0-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e2ec0-128">\<providerOption >, elemento</span><span class="sxs-lookup"><span data-stu-id="e2ec0-128">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="e2ec0-129">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e2ec0-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e2ec0-130">Parent Elements</span></span>

|<span data-ttu-id="e2ec0-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2ec0-131">Element</span></span>|<span data-ttu-id="e2ec0-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2ec0-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e2ec0-133">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="e2ec0-133">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="e2ec0-134">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="e2ec0-135">\<Elemento > de System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="e2ec0-135">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="e2ec0-136">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="e2ec0-137">\<compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="e2ec0-137">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="e2ec0-138">Contenedor para los elementos de configuración del compilador; contiene cero o más `<compiler>` elementos.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e2ec0-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2ec0-139">Remarks</span></span>

<span data-ttu-id="e2ec0-140">Cada `<compiler>` elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="e2ec0-141">El proveedor extiende la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> clase para un lenguaje específico; el `<compiler>` elemento define la configuración del compilador y del generador de código para el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="e2ec0-142">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e2ec0-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="e2ec0-143">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="e2ec0-144">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="e2ec0-145">Los elementos del compilador de la aplicación o el archivo de configuración Web pueden complementar o invalidar la configuración del archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="e2ec0-146">Si se configura más de una implementación de proveedor para el mismo nombre de idioma o la misma extensión de archivo, la última configuración coincidente invalida todos los proveedores configurados anteriormente para ese nombre de idioma o extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="e2ec0-147">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e2ec0-147">Configuration File</span></span>

<span data-ttu-id="e2ec0-148">Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2ec0-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="e2ec0-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2ec0-149">Example</span></span>

<span data-ttu-id="e2ec0-150">En el ejemplo siguiente se muestra un elemento de configuración de compilador típico:</span><span class="sxs-lookup"><span data-stu-id="e2ec0-150">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e2ec0-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ec0-151">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="e2ec0-152">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e2ec0-152">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e2ec0-153">\<compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="e2ec0-153">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="e2ec0-154">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="e2ec0-154">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="e2ec0-155">[Elemento Compiler para compiladores para compilation (esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e2ec0-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
