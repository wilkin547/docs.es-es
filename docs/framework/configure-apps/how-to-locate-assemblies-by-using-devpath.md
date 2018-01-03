---
title: "Cómo: Buscar ensamblados mediante DEVPATH"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4ee4200a67ef9d9d123be3bc32b02ac61512d23b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="1b0aa-102">Cómo: Buscar ensamblados mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="1b0aa-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="1b0aa-103">Los desarrolladores conviene asegurarse de que un ensamblado compartido que están generando funciona correctamente con varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="1b0aa-104">En lugar de poner constantemente el ensamblado en la caché global de ensamblados durante el ciclo de desarrollo, el programador puede crear una variable de entorno DEVPATH que señala al directorio de salida de compilación para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="1b0aa-105">Por ejemplo, suponga que está creando un ensamblado compartido denominado MySharedAssembly y que el directorio de resultados es C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="1b0aa-106">Se puede poner C:\MySharedAssembly\Debug en la variable DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="1b0aa-107">A continuación, debe especificar el [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="1b0aa-108">Este elemento indica a common language runtime que utilice DEVPATH al buscar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="1b0aa-109">El ensamblado compartido debe ser reconocible por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="1b0aa-110">Para especificar un directorio para resolver el uso de referencias de ensamblado privado el [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) o [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) en un archivo de configuración, como se describe en [Especificar la ubicación de un ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="1b0aa-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="1b0aa-111">También puede colocar el ensamblado en un subdirectorio del directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="1b0aa-112">Para más información, consulte [Cómo ubica ensamblados el tiempo de ejecución](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="1b0aa-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b0aa-113">Se trata de una característica avanzada, diseñada únicamente para su desarrollo.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="1b0aa-114">En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución buscar ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b0aa-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b0aa-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="1b0aa-116">El valor predeterminado es false.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b0aa-117">Use esta opción solo en tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-117">Use this setting only at development time.</span></span> <span data-ttu-id="1b0aa-118">El tiempo de ejecución no comprueba las versiones de ensamblados con nombre seguro que se encuentran en la variable DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="1b0aa-119">Simplemente utiliza el primer ensamblado que encuentre.</span><span class="sxs-lookup"><span data-stu-id="1b0aa-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0aa-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b0aa-120">See Also</span></span>  
 [<span data-ttu-id="1b0aa-121">Configurar aplicaciones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1b0aa-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
