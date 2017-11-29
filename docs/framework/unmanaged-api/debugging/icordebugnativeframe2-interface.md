---
title: ICorDebugNativeFrame2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2
helpviewer_keywords: ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c33eaa36313f0cf6aae904761fb40bb2dbf9d753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="acb9f-102">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="acb9f-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="acb9f-103">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="acb9f-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acb9f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="acb9f-104">Methods</span></span>  
  
|<span data-ttu-id="acb9f-105">Método</span><span class="sxs-lookup"><span data-stu-id="acb9f-105">Method</span></span>|<span data-ttu-id="acb9f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="acb9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acb9f-107">IsChild (método)</span><span class="sxs-lookup"><span data-stu-id="acb9f-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="acb9f-108">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="acb9f-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="acb9f-109">IsMatchingParentFrame (método)</span><span class="sxs-lookup"><span data-stu-id="acb9f-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="acb9f-110">Determina si el marco especificado es el elemento primario del fotograma actual.</span><span class="sxs-lookup"><span data-stu-id="acb9f-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="acb9f-111">GetStackParameterSize (método)</span><span class="sxs-lookup"><span data-stu-id="acb9f-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="acb9f-112">Devuelve el tamaño acumulado de los parámetros en la pila en x86 sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="acb9f-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acb9f-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acb9f-113">Remarks</span></span>  
 <span data-ttu-id="acb9f-114">Esta interfaz extiende lógicamente la interfaz "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="acb9f-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acb9f-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="acb9f-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acb9f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acb9f-116">Requirements</span></span>  
 <span data-ttu-id="acb9f-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acb9f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb9f-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acb9f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acb9f-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acb9f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acb9f-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acb9f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb9f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="acb9f-121">See Also</span></span>  
    
 [<span data-ttu-id="acb9f-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="acb9f-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="acb9f-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="acb9f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
