---
title: Procedimiento para buscar ensamblados mediante DEVPATH
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 6fa864f814d6a9ce04f2bce92c61cd0075ab5145
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912997"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="e66d8-102">Procedimiento para buscar ensamblados mediante DEVPATH</span><span class="sxs-lookup"><span data-stu-id="e66d8-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="e66d8-103">Los desarrolladores pueden querer asegurarse de que un ensamblado compartido que se está compilando funciona correctamente con varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e66d8-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="e66d8-104">En lugar de colocar continuamente el ensamblado en la caché global de ensamblados durante el ciclo de desarrollo, el desarrollador puede crear una variable de entorno DEVPATH que apunte al directorio de resultados de la compilación para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e66d8-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="e66d8-105">Por ejemplo, suponga que está creando un ensamblado compartido denominado MySharedAssembly y que el directorio de salida es C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="e66d8-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="e66d8-106">Puede colocar C:\MySharedAssembly\Debug en la variable DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e66d8-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="e66d8-107">A continuación, debe especificar el [ \<elemento > developmentMode](./file-schema/runtime/developmentmode-element.md) en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="e66d8-107">You must then specify the [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="e66d8-108">Este elemento indica al Common Language Runtime que utilice DEVPATH para buscar ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e66d8-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="e66d8-109">El tiempo de ejecución debe poder detectar el ensamblado compartido.</span><span class="sxs-lookup"><span data-stu-id="e66d8-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="e66d8-110">Para especificar un directorio privado para resolver las referencias de ensamblado, use el [ \<elemento codebase > elemento](./file-schema/runtime/codebase-element.md) o [ \<sondeo > elemento](./file-schema/runtime/probing-element.md) en un archivo de configuración, tal como se describe en [especificar la ubicación de un ensamblado](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="e66d8-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](./file-schema/runtime/codebase-element.md) or [\<probing> Element](./file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>  <span data-ttu-id="e66d8-111">También puede colocar el ensamblado en un subdirectorio del directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e66d8-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="e66d8-112">Para más información, consulte [Cómo ubica ensamblados el tiempo de ejecución](../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e66d8-112">For more information, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e66d8-113">Se trata de una característica avanzada, diseñada solo para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e66d8-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="e66d8-114">En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución busque ensamblados en los directorios especificados por la variable de entorno DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e66d8-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e66d8-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e66d8-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="e66d8-116">El valor predeterminado es false.</span><span class="sxs-lookup"><span data-stu-id="e66d8-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e66d8-117">Use esta configuración solo en tiempo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e66d8-117">Use this setting only at development time.</span></span> <span data-ttu-id="e66d8-118">El motor en tiempo de ejecución no comprueba las versiones de los ensamblados con nombre seguro que se encuentran en la DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="e66d8-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="e66d8-119">Simplemente usa el primer ensamblado que encuentra.</span><span class="sxs-lookup"><span data-stu-id="e66d8-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66d8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e66d8-120">See also</span></span>

- [<span data-ttu-id="e66d8-121">Configuración de aplicaciones mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e66d8-121">Configuring Apps by using Configuration Files</span></span>](index.md)
