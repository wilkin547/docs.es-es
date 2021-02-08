---
description: 'Más información acerca de: interfaz IHostControl'
title: IHostControl (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: e7a242ed0fdaa734425bec9b48f01fe45cba5182
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789468"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="04927-103">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04927-103">IHostControl Interface</span></span>

<span data-ttu-id="04927-104">Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.</span><span class="sxs-lookup"><span data-stu-id="04927-104">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04927-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="04927-105">Methods</span></span>  
  
|<span data-ttu-id="04927-106">Método</span><span class="sxs-lookup"><span data-stu-id="04927-106">Method</span></span>|<span data-ttu-id="04927-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="04927-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04927-108">Método GetHostManager</span><span class="sxs-lookup"><span data-stu-id="04927-108">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="04927-109">Obtiene un puntero de interfaz a la implementación del host de la interfaz con el especificado `IID` .</span><span class="sxs-lookup"><span data-stu-id="04927-109">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="04927-110">Método SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="04927-110">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="04927-111">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="04927-111">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04927-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04927-112">Requirements</span></span>  

 <span data-ttu-id="04927-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04927-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04927-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04927-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04927-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04927-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04927-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04927-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04927-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="04927-117">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="04927-118">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04927-118">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="04927-119">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04927-119">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="04927-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="04927-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
