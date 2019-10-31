---
title: ICorPublishProcess::IsManaged (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: ad3a357a98cb5ed28a34e4076b5e145903ceaf91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103500"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="391a8-102">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="391a8-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="391a8-103">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="391a8-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="391a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="391a8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="391a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="391a8-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="391a8-106">enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="391a8-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="391a8-107">El valor es `true` si el proceso tiene código administrado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="391a8-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="391a8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="391a8-108">Remarks</span></span>  
 <span data-ttu-id="391a8-109">Dado que la versión actual de `ICorPublishProcess` permite el acceso únicamente a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="391a8-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="391a8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="391a8-110">Requirements</span></span>  
 <span data-ttu-id="391a8-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="391a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="391a8-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="391a8-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="391a8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="391a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="391a8-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="391a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="391a8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="391a8-115">See also</span></span>

- [<span data-ttu-id="391a8-116">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="391a8-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
