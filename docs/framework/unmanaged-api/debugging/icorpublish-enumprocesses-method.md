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
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121798"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="aea08-102">ICorPublish::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="aea08-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="aea08-103">Obtiene un enumerador para los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="aea08-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea08-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aea08-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aea08-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aea08-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="aea08-106">Valor de la enumeración [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) que especifica el tipo de proceso que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="aea08-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="aea08-107">En la versión actual, solo COR_PUB_MANAGEDONLY es válido.</span><span class="sxs-lookup"><span data-stu-id="aea08-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="aea08-108">Puntero a la dirección de una instancia de [ICorPublishProcessEnum (](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) que es el enumerador de los procesos.</span><span class="sxs-lookup"><span data-stu-id="aea08-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aea08-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aea08-109">Remarks</span></span>  
 <span data-ttu-id="aea08-110">La colección de procesos del enumerador se basa en una instantánea de los procesos que se están ejecutando cuando se llama al método `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="aea08-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="aea08-111">El enumerador no incluirá ningún proceso que finalice antes o iniciar después de llamar a `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="aea08-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="aea08-112">Se puede llamar al método `EnumProcesses` más de una vez en esta instancia de [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) para crear una nueva colección de procesos actualizada.</span><span class="sxs-lookup"><span data-stu-id="aea08-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="aea08-113">Las llamadas subsiguientes del método `EnumProcesses` no afectarán a las colecciones existentes.</span><span class="sxs-lookup"><span data-stu-id="aea08-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aea08-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aea08-114">Requirements</span></span>  
 <span data-ttu-id="aea08-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aea08-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aea08-116">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="aea08-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="aea08-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aea08-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aea08-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aea08-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea08-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aea08-119">See also</span></span>

- [<span data-ttu-id="aea08-120">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aea08-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
