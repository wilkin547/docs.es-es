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
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178420"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="ef6e1-102">ICorPublish::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="ef6e1-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="ef6e1-103">Obtiene un [ICorPublishProcess](icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="ef6e1-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef6e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef6e1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef6e1-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="ef6e1-106">[en] Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="ef6e1-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="ef6e1-107">[fuera] Puntero a la dirección `ICorPublishProcess` de una instancia que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="ef6e1-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef6e1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef6e1-108">Remarks</span></span>  
 <span data-ttu-id="ef6e1-109">`GetProcess`se produce un error si el proceso no existe o no es un proceso administrado que el usuario actual puede depurar.</span><span class="sxs-lookup"><span data-stu-id="ef6e1-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef6e1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef6e1-110">Requirements</span></span>  
 <span data-ttu-id="ef6e1-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef6e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef6e1-112">**Encabezado:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ef6e1-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ef6e1-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef6e1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef6e1-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef6e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6e1-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef6e1-115">See also</span></span>

- [<span data-ttu-id="ef6e1-116">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef6e1-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
