---
title: "Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ca43e4952f7ff457cf61c2c36334ab6213e50ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="ef635-102">Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName</span><span class="sxs-lookup"><span data-stu-id="ef635-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="ef635-103">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], ha cambiado el separador de ruta de acceso utilizado en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> de la barra diagonal inversa ("\\") utilizada en versiones anteriores de .NET Framework a una barra diagonal ("/").</span><span class="sxs-lookup"><span data-stu-id="ef635-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="ef635-104">Los objetos <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> se crean al llamar a una de las sobrecargas del método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ef635-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ef635-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="ef635-105">Impact</span></span>  
 <span data-ttu-id="ef635-106">El cambio trae la implementación de .NET en conformidad con la sección 4.4.17.1 de la [Especificación de formato de archivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) y permite que los archivos ZIP se descompriman en sistemas distintos de Windows.</span><span class="sxs-lookup"><span data-stu-id="ef635-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="ef635-107">Al descomprimir un archivo zip creado por una aplicación que tiene como destino una versión anterior de .NET Framework en sistemas operativos que no son de Windows, como Macintosh, no se puede conservar la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="ef635-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="ef635-108">Por ejemplo, en Macintosh, crea un conjunto de archivos cuyo nombre de archivo concatena la ruta de acceso del directorio, junto con cualquier carácter de barra diagonal inversa ("\\") y el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ef635-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="ef635-109">Como resultado, no se conserva la estructura de directorios de archivos descomprimidos.</span><span class="sxs-lookup"><span data-stu-id="ef635-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="ef635-110">El impacto de este cambio en los archivos .zip que se descomprimen en el sistema operativo Windows por las API en el espacio de nombres de .NET Framework <xref:System.IO> debe ser mínimo, ya que estas API pueden controlar sin problemas una barra diagonal ("/") o una barra diagonal inversa ("\\") como carácter separador de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="ef635-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ef635-111">Mitigación</span><span class="sxs-lookup"><span data-stu-id="ef635-111">Mitigation</span></span>  
 <span data-ttu-id="ef635-112">Si no desea este comportamiento, puede rechazar la adición de un valor de configuración para la sección [ \<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef635-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="ef635-113">A continuación se muestra la sección `<runtime>` y el conmutador de rechazo.</span><span class="sxs-lookup"><span data-stu-id="ef635-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="ef635-114">Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones posteriores pueden incluirse en este comportamiento agregando un ajuste de configuración a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef635-114">In addition, apps that target previous versions of the .NET Framework but are running on the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="ef635-115">A continuación se muestra la sección `<runtime>` y el conmutador de inclusión.</span><span class="sxs-lookup"><span data-stu-id="ef635-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef635-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef635-116">See Also</span></span>  
 [<span data-ttu-id="ef635-117">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="ef635-117">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)  
 [<span data-ttu-id="ef635-118">Compatibilidad de aplicaciones en 4.6.1</span><span class="sxs-lookup"><span data-stu-id="ef635-118">Application Compatibility in 4.6.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
