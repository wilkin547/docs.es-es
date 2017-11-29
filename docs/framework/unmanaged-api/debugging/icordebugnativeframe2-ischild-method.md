---
title: "ICorDebugNativeFrame2::IsChild (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.IsChild Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 006543e473ca3b7cc1818b2b4641567ce37f6f0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="cd6d7-102">ICorDebugNativeFrame2::IsChild (Método)</span><span class="sxs-lookup"><span data-stu-id="cd6d7-102">ICorDebugNativeFrame2::IsChild Method</span></span>
<span data-ttu-id="cd6d7-103">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd6d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd6d7-104">Syntax</span></span>  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd6d7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd6d7-105">Parameters</span></span>  
 `pIsChild`  
 <span data-ttu-id="cd6d7-106">[out] Un valor booleano que especifica si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd6d7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd6d7-107">Return Value</span></span>  
 <span data-ttu-id="cd6d7-108">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cd6d7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd6d7-109">HRESULT</span></span>|<span data-ttu-id="cd6d7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd6d7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd6d7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd6d7-111">S_OK</span></span>|<span data-ttu-id="cd6d7-112">El estado del secundario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="cd6d7-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd6d7-113">E_FAIL</span></span>|<span data-ttu-id="cd6d7-114">No se pudo devolver el estado del secundario.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="cd6d7-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cd6d7-115">E_INVALIDARG</span></span>|<span data-ttu-id="cd6d7-116">`pIsChild` es null.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="cd6d7-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="cd6d7-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd6d7-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd6d7-118">Remarks</span></span>  
 <span data-ttu-id="cd6d7-119">El `IsChild` método `true` si el objeto de marco en el que se llama al método es un elemento secundario de otro marco.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="cd6d7-120">Si este es el caso, use la [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) método para comprobar si un marco es su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="cd6d7-120">If this is the case, use the [IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd6d7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd6d7-121">Requirements</span></span>  
 <span data-ttu-id="cd6d7-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd6d7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd6d7-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd6d7-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd6d7-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd6d7-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd6d7-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd6d7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd6d7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd6d7-126">See Also</span></span>  
 [<span data-ttu-id="cd6d7-127">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd6d7-127">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="cd6d7-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cd6d7-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cd6d7-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="cd6d7-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
