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
ms.openlocfilehash: ddf5af0bc0a5e5e21d837d8b2f3f76185ed7e2b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724720"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="a9116-102">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9116-102">ICorDebugNativeFrame2 Interface</span></span>

<span data-ttu-id="a9116-103">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="a9116-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9116-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a9116-104">Methods</span></span>  
  
|<span data-ttu-id="a9116-105">Método</span><span class="sxs-lookup"><span data-stu-id="a9116-105">Method</span></span>|<span data-ttu-id="a9116-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9116-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9116-107">Método IsChild</span><span class="sxs-lookup"><span data-stu-id="a9116-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="a9116-108">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="a9116-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="a9116-109">Método IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="a9116-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="a9116-110">Determina si el marco especificado es el elemento primario del marco actual.</span><span class="sxs-lookup"><span data-stu-id="a9116-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="a9116-111">Método GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="a9116-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="a9116-112">Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.</span><span class="sxs-lookup"><span data-stu-id="a9116-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9116-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9116-113">Remarks</span></span>  

 <span data-ttu-id="a9116-114">Esta interfaz extiende lógicamente la interfaz "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="a9116-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9116-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a9116-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9116-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9116-116">Requirements</span></span>  

 <span data-ttu-id="a9116-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9116-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9116-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9116-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9116-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9116-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9116-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9116-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9116-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9116-121">See also</span></span>

- [<span data-ttu-id="a9116-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a9116-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a9116-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="a9116-123">Debugging</span></span>](index.md)
