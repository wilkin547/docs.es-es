---
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
ms.openlocfilehash: 9dd89abb332853b966aa81dc506099b7af6ca3b2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804932"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="9dfa9-102">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dfa9-102">IHostControl Interface</span></span>
<span data-ttu-id="9dfa9-103">Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.</span><span class="sxs-lookup"><span data-stu-id="9dfa9-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9dfa9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9dfa9-104">Methods</span></span>  
  
|<span data-ttu-id="9dfa9-105">Método</span><span class="sxs-lookup"><span data-stu-id="9dfa9-105">Method</span></span>|<span data-ttu-id="9dfa9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dfa9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9dfa9-107">Método GetHostManager</span><span class="sxs-lookup"><span data-stu-id="9dfa9-107">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="9dfa9-108">Obtiene un puntero de interfaz a la implementación del host de la interfaz con el especificado `IID` .</span><span class="sxs-lookup"><span data-stu-id="9dfa9-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="9dfa9-109">Método SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="9dfa9-109">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="9dfa9-110">Notifica al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9dfa9-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9dfa9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dfa9-111">Requirements</span></span>  
 <span data-ttu-id="9dfa9-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dfa9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dfa9-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9dfa9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dfa9-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9dfa9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dfa9-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dfa9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfa9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9dfa9-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="9dfa9-117">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dfa9-117">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="9dfa9-118">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dfa9-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="9dfa9-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9dfa9-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
