---
title: Especificar la ubicación de un ensamblado
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: f7d09e315f2ccc7ecdcf22719ca6dce1ee1411b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186295"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="1a453-102">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="1a453-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="1a453-103">Hay dos maneras de especificar una ubicación de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="1a453-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="1a453-104">Mediante el [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1a453-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="1a453-105">Mediante el [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1a453-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="1a453-106">También puede usar el [herramienta de configuración de .NET Framework (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) para especificar ubicaciones de ensamblados o especificar ubicaciones para common language runtime sondear ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1a453-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="1a453-107">Mediante el \<codeBase > elemento</span><span class="sxs-lookup"><span data-stu-id="1a453-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="1a453-108">Puede usar el  **\<codeBase >** elemento sólo en configuración o publicador directiva archivos del equipo que también redirigir la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1a453-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="1a453-109">Cuando el tiempo de ejecución determina qué versión del ensamblado, se aplica el valor de la base de código del archivo que determina la versión.</span><span class="sxs-lookup"><span data-stu-id="1a453-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="1a453-110">Si no se indica ningún código base, el tiempo de ejecución sondea el ensamblado de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="1a453-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="1a453-111">Para obtener más información, consulte [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="1a453-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="1a453-112">El ejemplo siguiente muestra cómo especificar una ubicación de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1a453-112">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="1a453-113">El **versión** atributo es necesario para todos los ensamblados con nombre seguro, pero se debe omitir para los ensamblados que no tienen nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="1a453-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="1a453-114">El  **\<codeBase >** elemento requiere la **href** atributo.</span><span class="sxs-lookup"><span data-stu-id="1a453-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="1a453-115">No se puede especificar intervalos de versiones en el  **\<codeBase >** elemento.</span><span class="sxs-lookup"><span data-stu-id="1a453-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a453-116">Si se proporciona una sugerencia de base de código de un ensamblado que no tiene nombre seguro, la sugerencia debe apuntar a la base de la aplicación o en un subdirectorio del directorio base.</span><span class="sxs-lookup"><span data-stu-id="1a453-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="1a453-117">Mediante el \<probing > elemento</span><span class="sxs-lookup"><span data-stu-id="1a453-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="1a453-118">El tiempo de ejecución ubica ensamblados que no tienen un código base mediante sondeo.</span><span class="sxs-lookup"><span data-stu-id="1a453-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="1a453-119">Para obtener más información sobre las búsquedas, consulte [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="1a453-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="1a453-120">Puede usar el [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento en el archivo de configuración para especificar el tiempo de ejecución debe buscar para encontrar un ensamblado de subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="1a453-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="1a453-121">El ejemplo siguiente muestra cómo especificar los directorios que se debe buscar en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1a453-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="1a453-122">El **privatePath** atributo contiene los directorios que el tiempo de ejecución debe buscar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1a453-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="1a453-123">Si la aplicación se encuentra en C:\Program programa\myapp, el tiempo de ejecución busca ensamblados que no especifican un código base en C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin y C:\Program Files\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="1a453-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="1a453-124">Los directorios especificados en **privatePath** deben ser subdirectorios del directorio base.</span><span class="sxs-lookup"><span data-stu-id="1a453-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a453-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a453-125">See also</span></span>

- [<span data-ttu-id="1a453-126">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1a453-126">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="1a453-127">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="1a453-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="1a453-128">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="1a453-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="1a453-129">Configurar aplicaciones con archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1a453-129">Configuring Apps by using Configuration Files</span></span>](index.md)
