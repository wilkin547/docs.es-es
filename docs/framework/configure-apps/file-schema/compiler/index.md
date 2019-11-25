---
title: Esquema de configuración de compilador y proveedor de lenguaje
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: 5b1f9684ad26d4a03769af287fc8b0c0c7c4cc1a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088683"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="60d83-102">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="60d83-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="60d83-103">La configuración de compilador y proveedor de lenguaje especifica los elementos de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="60d83-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="60d83-104">Cada elemento de configuración de compilador especifica el nombre del tipo de proveedor de código, los parámetros del compilador, los nombres de lenguaje admitidos y las extensiones de archivo admitidas.</span><span class="sxs-lookup"><span data-stu-id="60d83-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
<span data-ttu-id="60d83-105">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="60d83-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="60d83-106">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="60d83-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="60d83-107">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="60d83-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
<span data-ttu-id="60d83-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60d83-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60d83-109">&nbsp;&nbsp;[ **\<> System. codedom**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="60d83-109">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="60d83-110">&nbsp;&nbsp;&nbsp;&nbsp;\<[**compiladores**](compilers-element.md) ></span><span class="sxs-lookup"><span data-stu-id="60d83-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\</span></span>
<span data-ttu-id="60d83-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[ **compilador** >](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="60d83-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>
  
|<span data-ttu-id="60d83-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="60d83-112">Element</span></span>|<span data-ttu-id="60d83-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="60d83-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60d83-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="60d83-114">\<system.codedom></span></span>](system-codedom-element.md)|<span data-ttu-id="60d83-115">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="60d83-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="60d83-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="60d83-116">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="60d83-117">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="60d83-117">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="60d83-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="60d83-118">\<compiler></span></span>](compiler-element.md)|<span data-ttu-id="60d83-119">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="60d83-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="60d83-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60d83-120">Example</span></span>  
 <span data-ttu-id="60d83-121">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="60d83-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="60d83-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="60d83-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="60d83-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="60d83-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="60d83-124">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="60d83-124">\<compiler> Element</span></span>](compiler-element.md)
