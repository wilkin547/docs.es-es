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
ms.openlocfilehash: 34753d538ff37ac4ae621f653d47ac92ac6749a0
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674469"
---
# <a name="compiler-element"></a><span data-ttu-id="64072-102">\<compilador > elemento</span><span class="sxs-lookup"><span data-stu-id="64072-102">\<compiler> Element</span></span>

<span data-ttu-id="64072-103">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="64072-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="64072-104">\<Elemento de configuración > \<elemento system.codedom > \<elemento compilers > \<compilador > elemento</span><span class="sxs-lookup"><span data-stu-id="64072-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="64072-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64072-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="64072-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="64072-106">Attributes and Elements</span></span>

<span data-ttu-id="64072-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="64072-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="64072-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="64072-108">Attributes</span></span>

|<span data-ttu-id="64072-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="64072-109">Attribute</span></span>|<span data-ttu-id="64072-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="64072-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="64072-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="64072-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64072-112">Especifica los argumentos específicos del compilador adicionales para la compilación.</span><span class="sxs-lookup"><span data-stu-id="64072-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="64072-113">Los valores para el `compilerOptions` atributo aparecen normalmente en un tema de las opciones del compilador para el compilador.</span><span class="sxs-lookup"><span data-stu-id="64072-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="64072-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="64072-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="64072-115">Proporciona una lista separada por comas de extensiones de nombre de archivo utilizado por los archivos de origen para el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="64072-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="64072-116">Por ejemplo, "cs".</span><span class="sxs-lookup"><span data-stu-id="64072-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="64072-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="64072-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="64072-118">Proporciona una lista separada por comas de nombres de lenguajes admitidos por el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="64072-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="64072-119">Por ejemplo, "C#; cs; csharp".</span><span class="sxs-lookup"><span data-stu-id="64072-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="64072-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="64072-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="64072-121">Especifica el nombre de tipo del proveedor del lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor.</span><span class="sxs-lookup"><span data-stu-id="64072-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="64072-122">El nombre de tipo debe cumplir los requisitos definidos en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="64072-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="64072-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="64072-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="64072-124">Especifica el nivel de advertencia del compilador predeterminado; Determina el nivel en el que el proveedor de lenguaje trata las advertencias de compilación como errores.</span><span class="sxs-lookup"><span data-stu-id="64072-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="64072-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="64072-125">Child Elements</span></span>

|<span data-ttu-id="64072-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="64072-126">Element</span></span>|<span data-ttu-id="64072-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="64072-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64072-128">\<providerOption > elemento</span><span class="sxs-lookup"><span data-stu-id="64072-128">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="64072-129">Especifica los atributos de versión del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="64072-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="64072-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64072-130">Parent Elements</span></span>

|<span data-ttu-id="64072-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="64072-131">Element</span></span>|<span data-ttu-id="64072-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="64072-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64072-133">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="64072-133">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="64072-134">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64072-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="64072-135">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="64072-135">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="64072-136">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="64072-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="64072-137">\<los compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="64072-137">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="64072-138">Contenedor para los elementos de configuración de compilador; contiene cero o más `<compiler>` elementos.</span><span class="sxs-lookup"><span data-stu-id="64072-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="64072-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64072-139">Remarks</span></span>

<span data-ttu-id="64072-140">Cada `<compiler>` elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.</span><span class="sxs-lookup"><span data-stu-id="64072-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="64072-141">Extiende el proveedor la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> clase para un idioma específico; el `<compiler>` elemento define el compilador y la configuración de generador de código para el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="64072-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="64072-142">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="64072-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="64072-143">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="64072-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="64072-144">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="64072-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="64072-145">Elementos de compilador de la aplicación o el archivo de configuración Web pueden complementar o reemplazar la configuración en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="64072-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="64072-146">Si se configura más de una implementación de proveedor para el mismo nombre de lenguaje o la misma extensión de archivo, la última configuración coincidente invalida cualquier proveedor configurado anteriormente para ese archivo o nombre de la extensión del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="64072-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="64072-147">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="64072-147">Configuration File</span></span>

<span data-ttu-id="64072-148">Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64072-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="64072-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64072-149">Example</span></span>

<span data-ttu-id="64072-150">El ejemplo siguiente muestra un elemento de configuración de compilador típico:</span><span class="sxs-lookup"><span data-stu-id="64072-150">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="64072-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="64072-151">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="64072-152">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="64072-152">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="64072-153">\<los compiladores > elemento</span><span class="sxs-lookup"><span data-stu-id="64072-153">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [<span data-ttu-id="64072-154">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="64072-154">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="64072-155">[Elemento Compiler aplicado a compilers para compilation (esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="64072-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
