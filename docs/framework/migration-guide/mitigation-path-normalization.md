---
title: 'Mitigación: Normalización de la ruta de acceso'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 61c8eec2043aa2fb9309ee6052e27fc2c91c6c6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181230"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="075dc-102">Mitigación: Normalización de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="075dc-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="075dc-103">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, la normalización de la ruta de acceso en .NET Framework ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="075dc-103">Starting with apps the target  the .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="075dc-104">¿Qué es la normalización de la ruta de acceso?</span><span class="sxs-lookup"><span data-stu-id="075dc-104">What is path normalization?</span></span>  
 <span data-ttu-id="075dc-105">La normalización de una ruta de acceso implica la modificación de la cadena que identifica a una ruta de acceso o archivo de manera que sea conforme con una ruta de acceso válida en el sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="075dc-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="075dc-106">La normalización implica normalmente:</span><span class="sxs-lookup"><span data-stu-id="075dc-106">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="075dc-107">La canonicalización del componente y los separadores de directorios.</span><span class="sxs-lookup"><span data-stu-id="075dc-107">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="075dc-108">La aplicación del directorio actual en una ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="075dc-108">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="075dc-109">La evaluación del directorio relativo (`.`) o el directorio principal (`..`) en una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="075dc-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="075dc-110">El recorte de caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="075dc-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="075dc-111">Cambios</span><span class="sxs-lookup"><span data-stu-id="075dc-111">The changes</span></span>  
 <span data-ttu-id="075dc-112">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, la normalización de la ruta de acceso ha cambiado de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="075dc-112">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="075dc-113">El tiempo de ejecución se aplaza para la función [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo con el objetivo de normalizar las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="075dc-113">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="075dc-114">La normalización ya no implica el recorte del final de los segmentos de directorio (como el espacio al final de un nombre de directorio).</span><span class="sxs-lookup"><span data-stu-id="075dc-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="075dc-115">Compatibilidad de la sintaxis de la ruta de acceso del dispositivo con plena confianza ( incluido `\\.\`) y, para las API de E/S del archivo en mscorlib.dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="075dc-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="075dc-116">El tiempo de ejecución o valida las rutas de acceso de la sintaxis del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="075dc-116">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="075dc-117">Es compatible el uso de la sintaxis del dispositivo para obtener acceso a los flujos de datos alternativos.</span><span class="sxs-lookup"><span data-stu-id="075dc-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="075dc-118">Impacto</span><span class="sxs-lookup"><span data-stu-id="075dc-118">Impact</span></span>  

<span data-ttu-id="075dc-119">Para las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior, estos cambios están activados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="075dc-119">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="075dc-120">Deben mejorar el rendimiento a la vez que permiten a los métodos obtener acceso a las rutas de acceso a las que no se podía obtener acceso anteriormente.</span><span class="sxs-lookup"><span data-stu-id="075dc-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="075dc-121">Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o posterior, no se ven afectadas por este cambio.</span><span class="sxs-lookup"><span data-stu-id="075dc-121">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="075dc-122">Mitigación</span><span class="sxs-lookup"><span data-stu-id="075dc-122">Mitigation</span></span>  
 <span data-ttu-id="075dc-123">Las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior pueden optar por no recibir este cambio y usar la normalización heredada agregando lo siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="075dc-123">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
<span data-ttu-id="075dc-124">Las aplicaciones que tienen como destino .NET Framework 4.6.1 o versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, pueden habilitar los cambios en la normalización de rutas de acceso agregando la línea siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="075dc-124">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="075dc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="075dc-125">See also</span></span>

- [<span data-ttu-id="075dc-126">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="075dc-126">Application compatibility</span></span>](application-compatibility.md)
