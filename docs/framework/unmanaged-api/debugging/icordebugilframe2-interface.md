---
title: Interfaz ICorDebugILFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4f57f27ec92e7977b46ebfa5967b0590674d2a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946476"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="af908-102">Interfaz ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="af908-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="af908-103">Una extensión lógica de ICorDebugILFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="af908-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af908-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="af908-104">Methods</span></span>  
  
|<span data-ttu-id="af908-105">Método</span><span class="sxs-lookup"><span data-stu-id="af908-105">Method</span></span>|<span data-ttu-id="af908-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="af908-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af908-107">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="af908-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="af908-108">Obtiene un objeto ICorDebugTypeEnum que contiene el <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="af908-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="af908-109">RemapFunction (método)</span><span class="sxs-lookup"><span data-stu-id="af908-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="af908-110">Reasigna una función editada especificando el nuevo desplazamiento MSIL.</span><span class="sxs-lookup"><span data-stu-id="af908-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af908-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af908-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af908-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="af908-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af908-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af908-113">Requirements</span></span>  
 <span data-ttu-id="af908-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af908-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af908-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af908-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af908-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af908-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af908-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af908-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af908-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="af908-118">See also</span></span>

- [<span data-ttu-id="af908-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="af908-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
