---
title: "ICorDebugThread3::CreateStackWalk (Método)"
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
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d3b587a69c7acc3115c282eac065d304dc892b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="c38ec-102">ICorDebugThread3::CreateStackWalk (Método)</span><span class="sxs-lookup"><span data-stu-id="c38ec-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="c38ec-103">Crea un [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="c38ec-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c38ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c38ec-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c38ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c38ec-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="c38ec-106">[out] Un puntero a la dirección de la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="c38ec-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c38ec-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c38ec-107">Return Value</span></span>  
 <span data-ttu-id="c38ec-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="c38ec-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c38ec-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c38ec-109">HRESULT</span></span>|<span data-ttu-id="c38ec-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c38ec-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c38ec-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c38ec-111">S_OK</span></span>|<span data-ttu-id="c38ec-112">La `ICorDebugStackWalk` objeto se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c38ec-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="c38ec-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c38ec-113">E_FAIL</span></span>|<span data-ttu-id="c38ec-114">El `ICorDebugStackWalk` no se creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="c38ec-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c38ec-115">Excepciones</span><span class="sxs-lookup"><span data-stu-id="c38ec-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c38ec-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c38ec-116">Remarks</span></span>  
 <span data-ttu-id="c38ec-117">Si el `CreateStackWalk` método tiene éxito, el valor devuelto `ICorDebugStackWalk` contexto del objeto se establece en el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c38ec-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c38ec-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c38ec-118">Requirements</span></span>  
 <span data-ttu-id="c38ec-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c38ec-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c38ec-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c38ec-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c38ec-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c38ec-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c38ec-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c38ec-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c38ec-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c38ec-123">See Also</span></span>  
 [<span data-ttu-id="c38ec-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c38ec-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c38ec-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="c38ec-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
