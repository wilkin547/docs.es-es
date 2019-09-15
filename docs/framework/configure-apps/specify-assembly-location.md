---
title: Especificar la ubicación de un ensamblado
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: f13b19dcd0aceac969d9639e6230ad33c6cd8d84
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971549"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="8d808-102">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="8d808-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="8d808-103">Hay dos maneras de especificar la ubicación de un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="8d808-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="8d808-104">Usar el elemento de [ \<> codebase](./file-schema/runtime/codebase-element.md) .</span><span class="sxs-lookup"><span data-stu-id="8d808-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="8d808-105">Usar el elemento de [ \<> de sondeo](./file-schema/runtime/probing-element.md) .</span><span class="sxs-lookup"><span data-stu-id="8d808-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="8d808-106">También puede usar la [herramienta de configuración de .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) para especificar ubicaciones de ensamblados o especificar ubicaciones para la Common Language Runtime para sondear ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8d808-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="8d808-107">Usar el \<elemento codebase ></span><span class="sxs-lookup"><span data-stu-id="8d808-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="8d808-108">Solo puede utilizar el  **\<elemento codebase >** en archivos de configuración de la máquina o de directiva de edición que también redirijan la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8d808-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="8d808-109">Cuando el tiempo de ejecución determina la versión de ensamblado que se va a usar, aplica la configuración de base de código del archivo que determina la versión.</span><span class="sxs-lookup"><span data-stu-id="8d808-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="8d808-110">Si no se indica ninguna base de código, el tiempo de ejecución sondea el ensamblado de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="8d808-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="8d808-111">Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="8d808-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="8d808-112">En el ejemplo siguiente se muestra cómo especificar la ubicación de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8d808-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="8d808-113">El atributo **version** es necesario para todos los ensamblados con nombre seguro, pero debe omitirse para los ensamblados que no tengan un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="8d808-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="8d808-114">**El\<elemento codebase >** requiere el atributo **href** .</span><span class="sxs-lookup"><span data-stu-id="8d808-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="8d808-115">No se pueden especificar intervalos de versiones en el  **\<elemento codebase >** .</span><span class="sxs-lookup"><span data-stu-id="8d808-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d808-116">Si va a proporcionar una sugerencia base de código para un ensamblado que no tiene un nombre seguro, la sugerencia debe apuntar a la base de la aplicación o a un subdirectorio del directorio base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d808-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="8d808-117">Usar el \<elemento de > de sondeo</span><span class="sxs-lookup"><span data-stu-id="8d808-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="8d808-118">El motor en tiempo de ejecución ubica los ensamblados que no tienen una base de código mediante sondeo.</span><span class="sxs-lookup"><span data-stu-id="8d808-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="8d808-119">Para obtener más información sobre el sondeo, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="8d808-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="8d808-120">Puede usar el [ \<elemento de > de sondeo](./file-schema/runtime/probing-element.md) del archivo de configuración de la aplicación para especificar subdirectorios en los que el tiempo de ejecución debe buscar al localizar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8d808-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="8d808-121">En el ejemplo siguiente se muestra cómo especificar los directorios en los que debe buscar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8d808-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="8d808-122">El atributo **privatePath** contiene los directorios en los que el tiempo de ejecución debe buscar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8d808-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="8d808-123">Si la aplicación se encuentra en C:\Archivos de Programa\myapp, el tiempo de ejecución buscará los ensamblados que no especifiquen una base de código en C:\Archivos de Files\MyApp\Bin, C:\Archivos de Files\MyApp\Bin2\Subbin y C:\Program Files\MyApp\Bin3.</span><span class="sxs-lookup"><span data-stu-id="8d808-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="8d808-124">Los directorios especificados en **privatePath** deben ser subdirectorios del directorio base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d808-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d808-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d808-125">See also</span></span>

- [<span data-ttu-id="8d808-126">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="8d808-126">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="8d808-127">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="8d808-127">Programming with Assemblies</span></span>](../../standard/assembly/program.md)
- [<span data-ttu-id="8d808-128">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="8d808-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="8d808-129">Configuración de aplicaciones mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8d808-129">Configuring Apps by using Configuration Files</span></span>](index.md)
