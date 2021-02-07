---
description: 'Más información acerca de: interfaz ICorDebugNativeFrame2'
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
ms.openlocfilehash: 9ed0e20bb29bef3b210258956ebecb1ee7a96df8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722352"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="5b3bf-103">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b3bf-103">ICorDebugNativeFrame2 Interface</span></span>

<span data-ttu-id="5b3bf-104">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="5b3bf-104">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b3bf-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5b3bf-105">Methods</span></span>  
  
|<span data-ttu-id="5b3bf-106">Método</span><span class="sxs-lookup"><span data-stu-id="5b3bf-106">Method</span></span>|<span data-ttu-id="5b3bf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b3bf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b3bf-108">Método IsChild</span><span class="sxs-lookup"><span data-stu-id="5b3bf-108">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="5b3bf-109">Determina si el marco actual es un marco secundario.</span><span class="sxs-lookup"><span data-stu-id="5b3bf-109">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="5b3bf-110">Método IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="5b3bf-110">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="5b3bf-111">Determina si el marco especificado es el elemento primario del marco actual.</span><span class="sxs-lookup"><span data-stu-id="5b3bf-111">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="5b3bf-112">Método GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="5b3bf-112">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="5b3bf-113">Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.</span><span class="sxs-lookup"><span data-stu-id="5b3bf-113">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b3bf-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b3bf-114">Remarks</span></span>  

 <span data-ttu-id="5b3bf-115">Esta interfaz extiende lógicamente la interfaz "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="5b3bf-115">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b3bf-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5b3bf-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b3bf-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b3bf-117">Requirements</span></span>  

 <span data-ttu-id="5b3bf-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b3bf-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b3bf-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b3bf-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b3bf-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b3bf-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b3bf-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b3bf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3bf-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b3bf-122">See also</span></span>

- [<span data-ttu-id="5b3bf-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5b3bf-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5b3bf-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="5b3bf-124">Debugging</span></span>](index.md)
