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
ms.openlocfilehash: 04f6a088c5bbe96e3909ba600aa8ffab937abe2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140403"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="daaca-102">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="daaca-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="daaca-103">Proporciona métodos que tienen acceso a la información que se va a mostrar sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="daaca-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="daaca-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="daaca-104">Methods</span></span>  
  
|<span data-ttu-id="daaca-105">Método</span><span class="sxs-lookup"><span data-stu-id="daaca-105">Method</span></span>|<span data-ttu-id="daaca-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="daaca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="daaca-107">EnumAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="daaca-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="daaca-108">Obtiene una instancia de [ICorPublishAppDomainEnum (](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) que contiene los dominios de aplicación en el proceso al que hace referencia este `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="daaca-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="daaca-109">GetDisplayName (método)</span><span class="sxs-lookup"><span data-stu-id="daaca-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="daaca-110">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia este `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="daaca-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="daaca-111">GetProcessID (método)</span><span class="sxs-lookup"><span data-stu-id="daaca-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="daaca-112">Obtiene el identificador del sistema operativo para el proceso al que hace referencia este `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="daaca-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="daaca-113">IsManaged (método)</span><span class="sxs-lookup"><span data-stu-id="daaca-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="daaca-114">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta `ICorPublishProcess` está ejecutando código administrado.</span><span class="sxs-lookup"><span data-stu-id="daaca-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="daaca-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="daaca-115">Requirements</span></span>  
 <span data-ttu-id="daaca-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daaca-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daaca-117">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="daaca-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="daaca-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daaca-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daaca-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daaca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daaca-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="daaca-120">See also</span></span>

- [<span data-ttu-id="daaca-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="daaca-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="daaca-122">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="daaca-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
