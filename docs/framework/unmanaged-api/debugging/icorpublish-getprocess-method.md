---
title: ICorPublish::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: a45f613b7547e2e80abdbd8ac85cb0b2b6a499e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716894"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="bd9c3-102">ICorPublish::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="bd9c3-102">ICorPublish::GetProcess Method</span></span>

<span data-ttu-id="bd9c3-103">Obtiene una instancia de [ICorPublishProcess](icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="bd9c3-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd9c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd9c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd9c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd9c3-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="bd9c3-106">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="bd9c3-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="bd9c3-107">enuncia Puntero a la dirección de una `ICorPublishProcess` instancia de que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="bd9c3-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd9c3-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd9c3-108">Remarks</span></span>  

 <span data-ttu-id="bd9c3-109">`GetProcess` se produce un error si el proceso no existe o no es un proceso administrado que el usuario actual puede depurar.</span><span class="sxs-lookup"><span data-stu-id="bd9c3-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd9c3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd9c3-110">Requirements</span></span>  

 <span data-ttu-id="bd9c3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd9c3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd9c3-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="bd9c3-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bd9c3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd9c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd9c3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd9c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9c3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd9c3-115">See also</span></span>

- [<span data-ttu-id="bd9c3-116">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd9c3-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
