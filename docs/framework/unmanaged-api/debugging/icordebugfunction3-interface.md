---
title: ICorDebugFunction3 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction3
api_location: mscordbi.dll
api_type: COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfe0c420c1c9b8074b7cb769e592f8cb2f5916e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="58a4b-102">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="58a4b-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="58a4b-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="58a4b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="58a4b-104">Extiende lógicamente la ICorDebugFunction (interfaz) para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="58a4b-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58a4b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="58a4b-105">Methods</span></span>  
  
|<span data-ttu-id="58a4b-106">Método</span><span class="sxs-lookup"><span data-stu-id="58a4b-106">Method</span></span>|<span data-ttu-id="58a4b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="58a4b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58a4b-108">GetActiveReJitRequestILCode (método)</span><span class="sxs-lookup"><span data-stu-id="58a4b-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="58a4b-109">Obtiene un puntero de interfaz a una [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el IL de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="58a4b-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58a4b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58a4b-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58a4b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58a4b-111">Requirements</span></span>  
 <span data-ttu-id="58a4b-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58a4b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58a4b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58a4b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58a4b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58a4b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58a4b-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58a4b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a4b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="58a4b-116">See Also</span></span>  
 [<span data-ttu-id="58a4b-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="58a4b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="58a4b-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="58a4b-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="58a4b-119">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="58a4b-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
