---
title: 'Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b97436ca2f81fea139689c7c2c2348718827b90f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70778865"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="18bf1-102">Mitigación: separador de ruta de acceso ZipArchiveEntry.FullName</span><span class="sxs-lookup"><span data-stu-id="18bf1-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="18bf1-103">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.1, ha cambiado el separador de ruta de acceso utilizado en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> de la barra diagonal inversa ("\\") utilizada en versiones anteriores de .NET Framework a una barra diagonal ("/").</span><span class="sxs-lookup"><span data-stu-id="18bf1-103">Starting with apps that target the .NET Framework 4.6.1, the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="18bf1-104">Los objetos <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> se crean al llamar a una de las sobrecargas del método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="18bf1-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="18bf1-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="18bf1-105">Impact</span></span>  
 <span data-ttu-id="18bf1-106">El cambio trae la implementación de .NET en conformidad con la sección 4.4.17.1 de la [Especificación de formato de archivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) y permite que los archivos ZIP se descompriman en sistemas distintos de Windows.</span><span class="sxs-lookup"><span data-stu-id="18bf1-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="18bf1-107">Al descomprimir un archivo zip creado por una aplicación que tiene como destino una versión anterior de .NET Framework en sistemas operativos que no son de Windows, como Macintosh, no se puede conservar la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="18bf1-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="18bf1-108">Por ejemplo, en Macintosh, crea un conjunto de archivos cuyo nombre de archivo concatena la ruta de acceso del directorio, junto con cualquier carácter de barra diagonal inversa ("\\") y el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="18bf1-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="18bf1-109">Como resultado, no se conserva la estructura de directorios de archivos descomprimidos.</span><span class="sxs-lookup"><span data-stu-id="18bf1-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="18bf1-110">El impacto de este cambio en los archivos .zip que se descomprimen en el sistema operativo Windows por las API en el espacio de nombres de .NET Framework <xref:System.IO> debe ser mínimo, ya que estas API pueden controlar sin problemas una barra diagonal ("/") o una barra diagonal inversa ("\\") como carácter separador de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="18bf1-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="18bf1-111">Mitigación</span><span class="sxs-lookup"><span data-stu-id="18bf1-111">Mitigation</span></span>  
 <span data-ttu-id="18bf1-112">Si no desea este comportamiento, puede rechazar la adición de un valor de configuración para la sección [ \<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18bf1-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="18bf1-113">A continuación se muestra la sección `<runtime>` y el conmutador de rechazo.</span><span class="sxs-lookup"><span data-stu-id="18bf1-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="18bf1-114">Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en .NET Framework 4.6.1 y versiones posteriores se pueden incluir en este comportamiento si se agrega una opción de configuración a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="18bf1-114">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="18bf1-115">A continuación se muestra la sección `<runtime>` y el conmutador de inclusión.</span><span class="sxs-lookup"><span data-stu-id="18bf1-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18bf1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="18bf1-116">See also</span></span>

- [<span data-ttu-id="18bf1-117">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="18bf1-117">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6-1.md)
- [<span data-ttu-id="18bf1-118">Compatibilidad de aplicaciones en 4.6.1</span><span class="sxs-lookup"><span data-stu-id="18bf1-118">Application Compatibility in 4.6.1</span></span>](application-compatibility-in-the-net-framework-4-6-1.md)
