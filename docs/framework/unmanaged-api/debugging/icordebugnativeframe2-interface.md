---
title: ICorDebugNativeFrame2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 638ce7933ededf2ff7b03b1c5aed7f6bdbfebc6c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912786"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="bebc1-102">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bebc1-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="bebc1-103">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="bebc1-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bebc1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bebc1-104">Methods</span></span>  
  
|<span data-ttu-id="bebc1-105">Método</span><span class="sxs-lookup"><span data-stu-id="bebc1-105">Method</span></span>|<span data-ttu-id="bebc1-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bebc1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bebc1-107">IsChild (método)</span><span class="sxs-lookup"><span data-stu-id="bebc1-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="bebc1-108">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="bebc1-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="bebc1-109">IsMatchingParentFrame (método)</span><span class="sxs-lookup"><span data-stu-id="bebc1-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="bebc1-110">Determina si el marco especificado es el elemento primario del marco actual.</span><span class="sxs-lookup"><span data-stu-id="bebc1-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="bebc1-111">GetStackParameterSize (método)</span><span class="sxs-lookup"><span data-stu-id="bebc1-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="bebc1-112">Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.</span><span class="sxs-lookup"><span data-stu-id="bebc1-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bebc1-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bebc1-113">Remarks</span></span>  
 <span data-ttu-id="bebc1-114">Esta interfaz extiende lógicamente la interfaz "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="bebc1-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bebc1-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="bebc1-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bebc1-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bebc1-116">Requirements</span></span>  
 <span data-ttu-id="bebc1-117">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bebc1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bebc1-118">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="bebc1-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bebc1-119">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bebc1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bebc1-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bebc1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bebc1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bebc1-121">See also</span></span>

- [<span data-ttu-id="bebc1-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bebc1-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bebc1-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="bebc1-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
