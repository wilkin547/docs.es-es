---
title: 'Mitigación: Normalización de la ruta de acceso'
description: Descubra cómo ha cambiado la normalización de la ruta de acceso en .NET Framework a partir de las aplicaciones que tienen como destino .NET Framework 4.6.2.
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 6f7e07690ab06fc7ef03344556c045405a63c374
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253601"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="f4dd7-103">Mitigación: normalización de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f4dd7-103">Mitigation: Path Normalization</span></span>

<span data-ttu-id="f4dd7-104">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, la normalización de la ruta de acceso en .NET Framework ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-104">Starting with apps that target .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="f4dd7-105">¿Qué es la normalización de la ruta de acceso?</span><span class="sxs-lookup"><span data-stu-id="f4dd7-105">What is path normalization?</span></span>  

 <span data-ttu-id="f4dd7-106">La normalización de una ruta de acceso implica la modificación de la cadena que identifica a una ruta de acceso o archivo de manera que sea conforme con una ruta de acceso válida en el sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-106">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="f4dd7-107">La normalización implica normalmente:</span><span class="sxs-lookup"><span data-stu-id="f4dd7-107">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="f4dd7-108">La canonicalización del componente y los separadores de directorios.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-108">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="f4dd7-109">La aplicación del directorio actual en una ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-109">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="f4dd7-110">La evaluación del directorio relativo (`.`) o el directorio principal (`..`) en una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-110">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="f4dd7-111">El recorte de caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-111">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="f4dd7-112">Cambios</span><span class="sxs-lookup"><span data-stu-id="f4dd7-112">The changes</span></span>  

 <span data-ttu-id="f4dd7-113">A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, la normalización de la ruta de acceso ha cambiado de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="f4dd7-113">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="f4dd7-114">El tiempo de ejecución se aplaza para la función [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo con el objetivo de normalizar las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-114">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="f4dd7-115">La normalización ya no implica el recorte del final de los segmentos de directorio (como el espacio al final de un nombre de directorio).</span><span class="sxs-lookup"><span data-stu-id="f4dd7-115">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="f4dd7-116">Compatibilidad de la sintaxis de la ruta de acceso del dispositivo con plena confianza ( incluido `\\.\`) y, para las API de E/S del archivo en mscorlib.dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-116">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="f4dd7-117">El tiempo de ejecución o valida las rutas de acceso de la sintaxis del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-117">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="f4dd7-118">Es compatible el uso de la sintaxis del dispositivo para obtener acceso a los flujos de datos alternativos.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-118">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="f4dd7-119">Impacto</span><span class="sxs-lookup"><span data-stu-id="f4dd7-119">Impact</span></span>  

<span data-ttu-id="f4dd7-120">Para las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior, estos cambios están activados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-120">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="f4dd7-121">Deben mejorar el rendimiento a la vez que permiten a los métodos obtener acceso a las rutas de acceso a las que no se podía obtener acceso anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-121">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="f4dd7-122">Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o posterior, no se ven afectadas por este cambio.</span><span class="sxs-lookup"><span data-stu-id="f4dd7-122">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="f4dd7-123">Mitigación</span><span class="sxs-lookup"><span data-stu-id="f4dd7-123">Mitigation</span></span>  

 <span data-ttu-id="f4dd7-124">Las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior pueden rechazar este cambio y usar la normalización heredada si se agrega lo siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f4dd7-124">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
<span data-ttu-id="f4dd7-125">Las aplicaciones que tienen como destino .NET Framework 4.6.1 o versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, pueden habilitar los cambios en la normalización de rutas de acceso si se agrega la línea siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo .configuration de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f4dd7-125">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4dd7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4dd7-126">See also</span></span>

- [<span data-ttu-id="f4dd7-127">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f4dd7-127">Application compatibility</span></span>](application-compatibility.md)
