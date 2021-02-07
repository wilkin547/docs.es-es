---
description: 'Más información acerca de: ICorPublish:: EnumProcesses (método)'
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
ms.openlocfilehash: 2451f179301eff4caca966568f966d145e269f51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722001"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="39984-103">ICorPublish::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="39984-103">ICorPublish::EnumProcesses Method</span></span>

<span data-ttu-id="39984-104">Obtiene un enumerador para los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="39984-104">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39984-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39984-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39984-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39984-106">Parameters</span></span>  

 `Type`  
 <span data-ttu-id="39984-107">Valor de la enumeración [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) que especifica el tipo de proceso que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="39984-107">A value of the [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="39984-108">En la versión actual, solo COR_PUB_MANAGEDONLY es válido.</span><span class="sxs-lookup"><span data-stu-id="39984-108">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="39984-109">Puntero a la dirección de una instancia de [ICorPublishProcessEnum (](icorpublishprocessenum-interface.md) que es el enumerador de los procesos.</span><span class="sxs-lookup"><span data-stu-id="39984-109">A pointer to the address of an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39984-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39984-110">Remarks</span></span>  

 <span data-ttu-id="39984-111">La colección de procesos del enumerador se basa en una instantánea de los procesos que se ejecutan cuando `EnumProcesses` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="39984-111">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="39984-112">El enumerador no incluirá los procesos que finalicen antes o después de que `EnumProcesses` se llame a.</span><span class="sxs-lookup"><span data-stu-id="39984-112">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="39984-113">`EnumProcesses`Se puede llamar al método más de una vez en esta instancia de [ICorPublish](icorpublish-interface.md) para crear una nueva colección de procesos actualizada.</span><span class="sxs-lookup"><span data-stu-id="39984-113">The `EnumProcesses` method may be called more than once on this [ICorPublish](icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="39984-114">Las llamadas subsiguientes del método no afectarán a las colecciones existentes `EnumProcesses` .</span><span class="sxs-lookup"><span data-stu-id="39984-114">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39984-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39984-115">Requirements</span></span>  

 <span data-ttu-id="39984-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39984-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39984-117">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="39984-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="39984-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39984-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39984-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39984-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39984-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="39984-120">See also</span></span>

- [<span data-ttu-id="39984-121">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39984-121">ICorPublish Interface</span></span>](icorpublish-interface.md)
