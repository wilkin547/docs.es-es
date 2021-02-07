---
description: 'Más información sobre: IAppDomainSetup (interfaz)'
title: IAppDomainSetup (Interfaz)
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 8fd224308ea68f7b56ae174c7f71fc4f89630101
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760589"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="1e8f6-103">IAppDomainSetup (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e8f6-103">IAppDomainSetup Interface</span></span>

<span data-ttu-id="1e8f6-104">Proporciona propiedades que permiten al host configurar un <xref:System.AppDomain?displayProperty=nameWithType> tipo antes de llamar al método [ICorRuntimeHost:: createdomainex (](icorruntimehost-createdomainex-method.md) para crearlo.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-104">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1e8f6-105">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1e8f6-105">Properties</span></span>  
  
|<span data-ttu-id="1e8f6-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1e8f6-106">Property</span></span>|<span data-ttu-id="1e8f6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e8f6-107">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="1e8f6-108">Obtiene o establece el nombre del directorio que contiene la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-108">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="1e8f6-109">Obtiene o establece el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-109">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="1e8f6-110">Obtiene o establece el nombre de un área específica de la aplicación donde se realiza la copia sombra de los archivos.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-110">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="1e8f6-111">Obtiene o establece el nombre del archivo de configuración de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-111">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="1e8f6-112">Obtiene o establece el nombre del directorio donde se almacenan los archivos generados dinámicamente y se obtiene acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-112">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="1e8f6-113">Obtiene o establece la ruta de acceso al archivo de licencia asociado a este dominio.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-113">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="1e8f6-114">Obtiene o establece la lista de directorios combinados con el <xref:System.AppDomainSetup.ApplicationBase%2A> directorio en el que se buscarán los ensamblados privados.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-114">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="1e8f6-115">Obtiene o establece un valor de cadena que incluye o excluye <xref:System.AppDomainSetup.ApplicationBase%2A> de la ruta de acceso de búsqueda para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-115">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="1e8f6-116">Obtiene o establece los nombres de los directorios que contienen los ensamblados de los que se va a realizar la instantánea.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-116">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="1e8f6-117">Obtiene o establece una cadena que indica si la copia sombra está activada o desactivada.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-117">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="1e8f6-118">Los valores válidos son "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="1e8f6-118">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e8f6-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e8f6-119">Remarks</span></span>  

 <span data-ttu-id="1e8f6-120">La `IAppDomainSetup` interfaz corresponde a la interfaz administrada <xref:System.IAppDomainSetup> , que <xref:System.AppDomainSetup> implementa el tipo.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-120">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="1e8f6-121">Vea <xref:System.IAppDomainSetup?displayProperty=nameWithType> para obtener descripciones detalladas de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-121">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="1e8f6-122">`IAppDomainSetup` representa la información de enlace del ensamblado que se puede Agregar a una <xref:System.AppDomain> instancia antes de su creación.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-122">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="1e8f6-123">Por ejemplo, un host puede establecer la <xref:System.AppDomainSetup.ApplicationBase%2A> propiedad para establecer un directorio raíz, en el que el Common Language Runtime (CLR) sondea para los ensamblados administrados.</span><span class="sxs-lookup"><span data-stu-id="1e8f6-123">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e8f6-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e8f6-124">Requirements</span></span>  

 <span data-ttu-id="1e8f6-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e8f6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e8f6-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1e8f6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e8f6-127">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e8f6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e8f6-128">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e8f6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8f6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e8f6-129">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="1e8f6-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1e8f6-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
