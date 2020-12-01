---
title: Configurar la redirección del enlace de ensamblados
description: Vea cómo configurar la redirección de enlace de ensamblados en .NET mediante el atributo appliesTo en el elemento assemblyBinding de un archivo de configuración de la aplicación.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
ms.openlocfilehash: 2455cab19132a208fb99454d4131363a624315c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236382"
---
# <a name="configuring-assembly-binding-redirection"></a><span data-ttu-id="29f2d-103">Configurar la redirección del enlace de ensamblados</span><span class="sxs-lookup"><span data-stu-id="29f2d-103">Configuring Assembly Binding Redirection</span></span>

<span data-ttu-id="29f2d-104">De forma predeterminada, las aplicaciones usan los ensamblados de .NET Framework que se incluyen con la versión del tiempo de ejecución usada para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29f2d-104">By default, applications use the set of .NET Framework assemblies that shipped with the runtime version used to compile the application.</span></span> <span data-ttu-id="29f2d-105">Puede usar el atributo **appliesTo** en el elemento [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) de un archivo de configuración de la aplicación para redirigir las referencias de enlace de ensamblados a una versión específica de los ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29f2d-105">You can use the **appliesTo** attribute on the [\<assemblyBinding>](../configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) element in an application configuration file to redirect assembly binding references to a specific version of the .NET Framework assemblies.</span></span> <span data-ttu-id="29f2d-106">Este atributo opcional usa un número de versión de .NET Framework para indicar a qué versión se aplica.</span><span class="sxs-lookup"><span data-stu-id="29f2d-106">This optional attribute uses a .NET Framework version number to indicate which version it applies to.</span></span> <span data-ttu-id="29f2d-107">Si no se especifica ningún atributo **appliesTo**, el elemento **\<assemblyBinding>** se aplica a todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29f2d-107">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="29f2d-108">El atributo **appliesTo** se incorporó en la versión 1.1 de .NET Framework; se pasa por alto en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29f2d-108">The **appliesTo** attribute was introduced in the .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="29f2d-109">Esto significa que se aplican todos los elementos **\<assemblyBinding>** cuando se usa la versión 1.0 de .NET Framework, aunque se especifique un atributo **appliesTo**.</span><span class="sxs-lookup"><span data-stu-id="29f2d-109">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29f2d-110">Use el atributo **appliesTo** para limitar la redirección de enlace de ensamblados a una versión específica del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="29f2d-110">Use the **appliesTo** attribute to limit assembly binding redirection to a specific version of the runtime.</span></span>  
  
 <span data-ttu-id="29f2d-111">Por ejemplo, para redirigir el enlace de un ensamblado de la versión 1.0 de .NET Framework, incluiría el siguiente código XML en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29f2d-111">For example, to redirect assembly binding for a .NET Framework version 1.0 assembly, you would include the following XML code in your application configuration file.</span></span>  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 <span data-ttu-id="29f2d-112">Los elementos **\<assemblyBinding>** tienen en cuenta el orden.</span><span class="sxs-lookup"><span data-stu-id="29f2d-112">The **\<assemblyBinding>** elements are order-sensitive.</span></span> <span data-ttu-id="29f2d-113">Primero debe especificar la información de redirección de enlace de los ensamblados de la versión 1.0 de .NET Framework, seguida de la información de redirección de enlace de los ensamblados de la versión 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29f2d-113">You should enter assembly binding redirection information for any .NET Framework version 1.0 assemblies first, followed by assembly binding redirection information for any .NET Framework version 1.1 assemblies.</span></span> <span data-ttu-id="29f2d-114">Por último, especifique la información de redirección de enlace de ensamblados para cualquier redirección de ensamblados de .NET Framework que no use el atributo **appliesTo** y, por tanto, se aplica a todas las versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29f2d-114">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="29f2d-115">En el caso de un conflicto en la redirección, se usa la primera instrucción de redirección que coincida en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="29f2d-115">In case of a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>  
  
 <span data-ttu-id="29f2d-116">Por ejemplo, para redirigir una referencia a un ensamblado de la versión 1.0 de .NET Framework y otra referencia a un ensamblado de la versión 1.1 de .NET Framework, usaría el patrón que se muestra en el siguiente pseudocódigo.</span><span class="sxs-lookup"><span data-stu-id="29f2d-116">For example, to redirect one reference to a .NET Framework version 1.0 assembly and another reference to a .NET Framework version 1.1 assembly, you would use the pattern shown in the following pseudocode.</span></span>  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">
  <!-- .NET Framework version 1.0 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">
  <!-- .NET Framework version 1.1 redirects here. -->
</assemblyBinding>
  
<assemblyBinding xmlns="...">
  <!-- Redirects meant for all versions of the .NET Framework. -->
</assemblyBinding>  
```  
  
## <a name="debugging-configuration-file-errors"></a><span data-ttu-id="29f2d-117">Depurar errores de archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="29f2d-117">Debugging Configuration File Errors</span></span>  

 <span data-ttu-id="29f2d-118">El tiempo de ejecución analiza los archivos de configuración una vez cuando se crea un dominio de aplicación y carga el código en ese dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29f2d-118">The runtime parses configuration files once when an application domain is created, and loads code into that application domain.</span></span> <span data-ttu-id="29f2d-119">Common Language Runtime controla los errores en un archivo de configuración omitiendo la entrada.</span><span class="sxs-lookup"><span data-stu-id="29f2d-119">The common language runtime handles errors in a configuration file by ignoring the entry.</span></span> <span data-ttu-id="29f2d-120">El tiempo de ejecución omite el archivo de configuración completo si contiene código XML con formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="29f2d-120">The runtime ignores the entire configuration file if it contains malformed XML.</span></span> <span data-ttu-id="29f2d-121">En el caso de código XML no válido, se omiten solo las secciones no válidas.</span><span class="sxs-lookup"><span data-stu-id="29f2d-121">For invalid XML, only the invalid sections are ignored.</span></span>  
  
 <span data-ttu-id="29f2d-122">Para determinar si un archivo de configuración se está usando, determine si se producen redirecciones de enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="29f2d-122">You can determine whether a configuration file is being used by determining whether assembly binding redirects are occurring.</span></span> <span data-ttu-id="29f2d-123">Use el [Visor de registro de enlaces de ensamblados (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) para ver qué ensamblados se van a cargar.</span><span class="sxs-lookup"><span data-stu-id="29f2d-123">Use the [Assembly Binding Log Viewer (Fuslogvw.exe)](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) to see which assemblies are being loaded.</span></span> <span data-ttu-id="29f2d-124">Para ver todos los enlaces de ensamblado, debe establecer una entrada para **ForceLog** en el Registro.</span><span class="sxs-lookup"><span data-stu-id="29f2d-124">To see all assembly binds, you must set an entry for **ForceLog** in the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f2d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="29f2d-125">See also</span></span>

- [<span data-ttu-id="29f2d-126">Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático</span><span class="sxs-lookup"><span data-stu-id="29f2d-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
