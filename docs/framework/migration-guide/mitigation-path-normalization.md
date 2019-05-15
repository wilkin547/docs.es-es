---
title: 'Mitigación: normalización de la ruta de acceso'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51291fbc9ad2927bc3b9649074a6dbf374aaf7f1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648449"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="84d0e-102">Mitigación: normalización de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="84d0e-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="84d0e-103">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalización de la ruta de acceso en .NET Framework ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="84d0e-103">Starting with apps the target  the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="84d0e-104">¿Qué es la normalización de la ruta de acceso?</span><span class="sxs-lookup"><span data-stu-id="84d0e-104">What is path normalization?</span></span>  
 <span data-ttu-id="84d0e-105">La normalización de una ruta de acceso implica la modificación de la cadena que identifica a una ruta de acceso o archivo de manera que sea conforme con una ruta de acceso válida en el sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="84d0e-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="84d0e-106">La normalización implica normalmente:</span><span class="sxs-lookup"><span data-stu-id="84d0e-106">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="84d0e-107">La canonicalización del componente y los separadores de directorios.</span><span class="sxs-lookup"><span data-stu-id="84d0e-107">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="84d0e-108">La aplicación del directorio actual en una ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="84d0e-108">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="84d0e-109">La evaluación del directorio relativo (`.`) o el directorio principal (`..`) en una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="84d0e-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="84d0e-110">El recorte de caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="84d0e-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="84d0e-111">Cambios</span><span class="sxs-lookup"><span data-stu-id="84d0e-111">The changes</span></span>  
 <span data-ttu-id="84d0e-112">A partir de las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalización de la ruta de acceso ha cambiado de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="84d0e-112">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="84d0e-113">El tiempo de ejecución se aplaza para la función [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo con el objetivo de normalizar las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="84d0e-113">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="84d0e-114">La normalización ya no implica el recorte del final de los segmentos de directorio (como el espacio al final de un nombre de directorio).</span><span class="sxs-lookup"><span data-stu-id="84d0e-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="84d0e-115">Compatibilidad de la sintaxis de la ruta de acceso del dispositivo con plena confianza ( incluido `\\.\`) y, para las API de E/S del archivo en mscorlib.dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="84d0e-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="84d0e-116">El tiempo de ejecución o valida las rutas de acceso de la sintaxis del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84d0e-116">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="84d0e-117">Es compatible el uso de la sintaxis del dispositivo para obtener acceso a los flujos de datos alternativos.</span><span class="sxs-lookup"><span data-stu-id="84d0e-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="84d0e-118">Impacto</span><span class="sxs-lookup"><span data-stu-id="84d0e-118">Impact</span></span>  
 <span data-ttu-id="84d0e-119">Para aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o posterior, estos cambios están activados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="84d0e-119">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later, these changes are on  by default.</span></span> <span data-ttu-id="84d0e-120">Deben mejorar el rendimiento a la vez que permiten a los métodos obtener acceso a las rutas de acceso a las que no se podía obtener acceso anteriormente.</span><span class="sxs-lookup"><span data-stu-id="84d0e-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
 <span data-ttu-id="84d0e-121">Las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o posterior, no se ven afectadas por este cambio.</span><span class="sxs-lookup"><span data-stu-id="84d0e-121">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions but are running under the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="84d0e-122">Mitigación</span><span class="sxs-lookup"><span data-stu-id="84d0e-122">Mitigation</span></span>  
 <span data-ttu-id="84d0e-123">Las aplicaciones que tienen como destino [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o posterior pueden rechazar este cambio y utilizar la normalización heredada agregando lo siguiente a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="84d0e-123">Apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 <span data-ttu-id="84d0e-124">Las aplicaciones que tienen como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versiones anteriores, pero que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versiones posteriores pueden habilitar los cambios en la normalización de rutas de acceso agregando la siguiente línea a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo .configuration de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="84d0e-124">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or earlier but are running on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84d0e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="84d0e-125">See also</span></span>

- [<span data-ttu-id="84d0e-126">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="84d0e-126">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
