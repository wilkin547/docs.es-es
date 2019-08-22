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
ms.openlocfilehash: 4900c391ae94447cdf4be331a27f6f3398e9129a
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659720"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="33bf8-102">Esquema de configuración de compilador y proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="33bf8-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="33bf8-103">La configuración de compilador y proveedor de lenguaje especifica los elementos de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="33bf8-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="33bf8-104">Cada elemento de configuración de compilador especifica el nombre del tipo de proveedor de código, los parámetros del compilador, los nombres de lenguaje admitidos y las extensiones de archivo admitidas.</span><span class="sxs-lookup"><span data-stu-id="33bf8-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
 <span data-ttu-id="33bf8-105">.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="33bf8-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="33bf8-106">Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.</span><span class="sxs-lookup"><span data-stu-id="33bf8-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="33bf8-107">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.</span><span class="sxs-lookup"><span data-stu-id="33bf8-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 [<span data-ttu-id="33bf8-108">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="33bf8-108">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="33bf8-109">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="33bf8-109">\<system.codedom></span></span>](system-codedom-element.md)  
  
 [<span data-ttu-id="33bf8-110">\<compilers></span><span class="sxs-lookup"><span data-stu-id="33bf8-110">\<compilers></span></span>](compilers-element.md)  
  
 [<span data-ttu-id="33bf8-111">\<compiler></span><span class="sxs-lookup"><span data-stu-id="33bf8-111">\<compiler></span></span>](compiler-element.md)  
  
|<span data-ttu-id="33bf8-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="33bf8-112">Element</span></span>|<span data-ttu-id="33bf8-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33bf8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33bf8-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="33bf8-114">\<system.codedom></span></span>](system-codedom-element.md)|<span data-ttu-id="33bf8-115">Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="33bf8-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="33bf8-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="33bf8-116">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="33bf8-117">Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="33bf8-117">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="33bf8-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="33bf8-118">\<compiler></span></span>](compiler-element.md)|<span data-ttu-id="33bf8-119">Especifica los atributos de configuración del compilador para un proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="33bf8-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="33bf8-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33bf8-120">Example</span></span>  
 <span data-ttu-id="33bf8-121">En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.</span><span class="sxs-lookup"><span data-stu-id="33bf8-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="33bf8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="33bf8-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="33bf8-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="33bf8-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="33bf8-124">Elemento \<compiler></span><span class="sxs-lookup"><span data-stu-id="33bf8-124">\<compiler> Element</span></span>](compiler-element.md)
