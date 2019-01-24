---
title: ICorDebugFunction3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e564ce63f7bf9e04ebf9a0bdcfc819ea23b3b2ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515565"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="b6c41-102">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6c41-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="b6c41-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b6c41-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b6c41-104">Extiende lógicamente la ICorDebugFunction (interfaz) para proporcionar acceso a código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="b6c41-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6c41-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b6c41-105">Methods</span></span>  
  
|<span data-ttu-id="b6c41-106">Método</span><span class="sxs-lookup"><span data-stu-id="b6c41-106">Method</span></span>|<span data-ttu-id="b6c41-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6c41-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6c41-108">GetActiveReJitRequestILCode (método)</span><span class="sxs-lookup"><span data-stu-id="b6c41-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="b6c41-109">Obtiene un puntero de interfaz a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el IL de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="b6c41-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6c41-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6c41-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c41-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6c41-111">Requirements</span></span>  
 <span data-ttu-id="b6c41-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6c41-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c41-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6c41-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6c41-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6c41-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6c41-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c41-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c41-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6c41-116">See also</span></span>
- [<span data-ttu-id="b6c41-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b6c41-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b6c41-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="b6c41-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b6c41-119">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="b6c41-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
