---
title: ICorDebugILFrame2 Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2
helpviewer_keywords: ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 759232d5c1e5bdf00c85145fa0fc3d69743c13f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="7a09f-102">ICorDebugILFrame2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="7a09f-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="7a09f-103">Una extensión lógica de ICorDebugILFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="7a09f-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a09f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7a09f-104">Methods</span></span>  
  
|<span data-ttu-id="7a09f-105">Método</span><span class="sxs-lookup"><span data-stu-id="7a09f-105">Method</span></span>|<span data-ttu-id="7a09f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a09f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a09f-107">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="7a09f-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="7a09f-108">Obtiene un objeto ICorDebugTypeEnum que contiene el <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="7a09f-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="7a09f-109">RemapFunction (método)</span><span class="sxs-lookup"><span data-stu-id="7a09f-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="7a09f-110">Reasigna una función editada especificando el nuevo desplazamiento MSIL.</span><span class="sxs-lookup"><span data-stu-id="7a09f-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a09f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7a09f-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a09f-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7a09f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a09f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a09f-113">Requirements</span></span>  
 <span data-ttu-id="7a09f-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a09f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a09f-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a09f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a09f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a09f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a09f-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a09f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a09f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a09f-118">See Also</span></span>  
 [<span data-ttu-id="7a09f-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7a09f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
