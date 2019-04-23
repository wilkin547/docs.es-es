---
title: ICorPublishProcess (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182967"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="aff6e-102">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aff6e-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="aff6e-103">Proporciona métodos que tienen acceso a mostrar información acerca de un proceso.</span><span class="sxs-lookup"><span data-stu-id="aff6e-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aff6e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="aff6e-104">Methods</span></span>  
  
|<span data-ttu-id="aff6e-105">Método</span><span class="sxs-lookup"><span data-stu-id="aff6e-105">Method</span></span>|<span data-ttu-id="aff6e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="aff6e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aff6e-107">EnumAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="aff6e-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="aff6e-108">Obtiene un [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instancia que contiene los dominios de aplicación en el proceso que hace referencia esta `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="aff6e-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="aff6e-109">GetDisplayName (método)</span><span class="sxs-lookup"><span data-stu-id="aff6e-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="aff6e-110">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso que hace referencia esta `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="aff6e-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="aff6e-111">GetProcessID (método)</span><span class="sxs-lookup"><span data-stu-id="aff6e-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="aff6e-112">Obtiene el identificador del sistema operativo para el proceso que hace referencia esta `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="aff6e-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="aff6e-113">IsManaged (método)</span><span class="sxs-lookup"><span data-stu-id="aff6e-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="aff6e-114">Obtiene un valor que indica si el proceso que hace referencia esta `ICorPublishProcess` se sabe que se ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="aff6e-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aff6e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aff6e-115">Requirements</span></span>  
 <span data-ttu-id="aff6e-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aff6e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aff6e-117">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="aff6e-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="aff6e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aff6e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aff6e-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aff6e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff6e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="aff6e-120">See also</span></span>

- [<span data-ttu-id="aff6e-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="aff6e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="aff6e-122">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="aff6e-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
