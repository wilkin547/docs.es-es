---
title: ICorDebugILCode2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d511999cac312c785e528cda24c215555a62ae76
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491173"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="00089-102">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00089-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="00089-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="00089-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="00089-104">Extiende lógicamente la [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaz para proporcionar métodos que devuelven el token de firma de variable local de una función, e instrumentada un lenguaje intermedio del generador de perfiles (IL) que asignan los desplazamientos al IL del método original desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="00089-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00089-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="00089-105">Methods</span></span>  
  
|<span data-ttu-id="00089-106">Método</span><span class="sxs-lookup"><span data-stu-id="00089-106">Method</span></span>|<span data-ttu-id="00089-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="00089-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00089-108">Método GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="00089-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="00089-109">Devuelve la correspondencia entre los desplazamientos del IL instrumentado del generador de perfiles y los desplazamientos del IL del método original para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="00089-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="00089-110">GetLocalVarSigToken (método)</span><span class="sxs-lookup"><span data-stu-id="00089-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="00089-111">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="00089-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00089-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00089-112">Requirements</span></span>  
 <span data-ttu-id="00089-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00089-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00089-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00089-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00089-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00089-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00089-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00089-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00089-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="00089-117">See also</span></span>
- [<span data-ttu-id="00089-118">ICorDebugILCode (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00089-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="00089-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="00089-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="00089-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="00089-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
