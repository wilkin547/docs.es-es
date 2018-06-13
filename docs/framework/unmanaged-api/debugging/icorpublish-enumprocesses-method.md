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
ms.openlocfilehash: 2779138a0999e34ad6424d76ddfebbcfdf611d58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422902"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="0030a-102">ICorPublish::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="0030a-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="0030a-103">Obtiene un enumerador para los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="0030a-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0030a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0030a-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0030a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0030a-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="0030a-106">Un valor de la [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeración que especifica el tipo de proceso va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0030a-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="0030a-107">En la versión actual, solamente es válido COR_PUB_MANAGEDONLY.</span><span class="sxs-lookup"><span data-stu-id="0030a-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="0030a-108">Un puntero a la dirección de un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instancia que es el enumerador de los procesos.</span><span class="sxs-lookup"><span data-stu-id="0030a-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0030a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0030a-109">Remarks</span></span>  
 <span data-ttu-id="0030a-110">Colección del enumerador de procesos se basa en una instantánea de los procesos que se ejecutan cuando el `EnumProcesses` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="0030a-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="0030a-111">El enumerador no incluirá los procesos que finalicen antes o se inician después de `EnumProcesses` se llama.</span><span class="sxs-lookup"><span data-stu-id="0030a-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="0030a-112">El `EnumProcesses` método puede llamarse varias veces en el objeto [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instancia para crear una nueva colección actualizada de procesos.</span><span class="sxs-lookup"><span data-stu-id="0030a-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="0030a-113">Las colecciones existentes no se verán afectadas por las llamadas subsiguientes de la `EnumProcesses` método.</span><span class="sxs-lookup"><span data-stu-id="0030a-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0030a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0030a-114">Requirements</span></span>  
 <span data-ttu-id="0030a-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0030a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0030a-116">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0030a-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0030a-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0030a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0030a-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0030a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0030a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0030a-119">See Also</span></span>  
 [<span data-ttu-id="0030a-120">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0030a-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
