---
title: ICorPublish::EnumProcesses (Método)
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4096b0ae083e0b6c0598ea18cc8b33c2fdfe3e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116300"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="0a77b-102">ICorPublish::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="0a77b-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="0a77b-103">Obtiene un enumerador para los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="0a77b-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a77b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a77b-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a77b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a77b-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="0a77b-106">Un valor de la [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeración que especifica el tipo de proceso que va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0a77b-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="0a77b-107">En la versión actual, COR_PUB_MANAGEDONLY solo es válida.</span><span class="sxs-lookup"><span data-stu-id="0a77b-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="0a77b-108">Un puntero a la dirección de un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que es el enumerador de los procesos.</span><span class="sxs-lookup"><span data-stu-id="0a77b-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a77b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a77b-109">Remarks</span></span>  
 <span data-ttu-id="0a77b-110">Colección del enumerador de procesos se basa en una instantánea de los procesos que se ejecutan cuando el `EnumProcesses` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="0a77b-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="0a77b-111">El enumerador no incluirá todos los procesos que finalicen antes o inician después `EnumProcesses` se llama.</span><span class="sxs-lookup"><span data-stu-id="0a77b-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="0a77b-112">El `EnumProcesses` método puede llamarse varias veces en este [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instancia para crear una nueva colección actualizada de los procesos.</span><span class="sxs-lookup"><span data-stu-id="0a77b-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="0a77b-113">Las colecciones existentes no se verán afectadas por las llamadas posteriores de la `EnumProcesses` método.</span><span class="sxs-lookup"><span data-stu-id="0a77b-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a77b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a77b-114">Requirements</span></span>  
 <span data-ttu-id="0a77b-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a77b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a77b-116">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0a77b-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0a77b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a77b-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0a77b-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0a77b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a77b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a77b-119">See also</span></span>

- [<span data-ttu-id="0a77b-120">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a77b-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
