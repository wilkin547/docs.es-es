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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee3a0c27d350dec8e9f3e9448174d978c7d50e81
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775686"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="e0116-102">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="e0116-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="e0116-103">Obtiene un valor que indica si el proceso que hace referencia esta [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) se sabe que tienen código administrado.</span><span class="sxs-lookup"><span data-stu-id="e0116-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0116-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0116-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0116-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0116-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="e0116-106">[out] Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="e0116-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="e0116-107">El valor es `true` si el proceso tiene código administrado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e0116-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0116-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0116-108">Remarks</span></span>  
 <span data-ttu-id="e0116-109">Desde la versión actual de `ICorPublishProcess` permite el acceso solo a los procesos que haya código administrado, `IsManaged` siempre devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="e0116-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0116-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0116-110">Requirements</span></span>  
 <span data-ttu-id="e0116-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0116-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0116-112">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="e0116-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e0116-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0116-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0116-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0116-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0116-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0116-115">See also</span></span>

- [<span data-ttu-id="e0116-116">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0116-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
