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
ms.openlocfilehash: 4c29d631f84ce2dd7532e32951e71d6597218ebb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088865"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="3b9ae-102">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b9ae-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="3b9ae-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="3b9ae-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3b9ae-104">Extiende lógicamente la ICorDebugFunction (interfaz) para proporcionar acceso a código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="3b9ae-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b9ae-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3b9ae-105">Methods</span></span>  
  
|<span data-ttu-id="3b9ae-106">Método</span><span class="sxs-lookup"><span data-stu-id="3b9ae-106">Method</span></span>|<span data-ttu-id="3b9ae-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b9ae-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b9ae-108">Método GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="3b9ae-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="3b9ae-109">Obtiene un puntero de interfaz a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el IL de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="3b9ae-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b9ae-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b9ae-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b9ae-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b9ae-111">Requirements</span></span>  
 <span data-ttu-id="3b9ae-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b9ae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b9ae-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b9ae-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b9ae-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b9ae-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3b9ae-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3b9ae-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b9ae-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b9ae-116">See also</span></span>

- [<span data-ttu-id="3b9ae-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3b9ae-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3b9ae-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="3b9ae-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3b9ae-119">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="3b9ae-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
