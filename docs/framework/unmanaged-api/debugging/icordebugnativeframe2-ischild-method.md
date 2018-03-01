---
title: "ICorDebugNativeFrame2::IsChild (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 267bc2fcd03786bfceb218dd0218ffa7006f8fa7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="f7ebf-102">ICorDebugNativeFrame2::IsChild (Método)</span><span class="sxs-lookup"><span data-stu-id="f7ebf-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="f7ebf-103">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ebf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7ebf-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7ebf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7ebf-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="f7ebf-106">[out] Un valor booleano que especifica si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7ebf-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7ebf-107">Return Value</span></span>  
 <span data-ttu-id="f7ebf-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f7ebf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7ebf-109">HRESULT</span></span>|<span data-ttu-id="f7ebf-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7ebf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7ebf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7ebf-111">S_OK</span></span>|<span data-ttu-id="f7ebf-112">El estado del secundario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="f7ebf-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7ebf-113">E_FAIL</span></span>|<span data-ttu-id="f7ebf-114">No se pudo devolver el estado del secundario.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="f7ebf-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f7ebf-115">E_INVALIDARG</span></span>|<span data-ttu-id="f7ebf-116">`pIsChild` es null.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f7ebf-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="f7ebf-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7ebf-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7ebf-118">Remarks</span></span>  
 <span data-ttu-id="f7ebf-119">El `IsChild` método `true` si el objeto de marco en el que se llama al método es un elemento secundario de otro marco.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="f7ebf-120">Si este es el caso, use la [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) método para comprobar si un marco es su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="f7ebf-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7ebf-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7ebf-121">Requirements</span></span>  
 <span data-ttu-id="f7ebf-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7ebf-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7ebf-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7ebf-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7ebf-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7ebf-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7ebf-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7ebf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ebf-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7ebf-126">See Also</span></span>  
 [<span data-ttu-id="f7ebf-127">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7ebf-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="f7ebf-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f7ebf-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f7ebf-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="f7ebf-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
