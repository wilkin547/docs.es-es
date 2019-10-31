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
ms.openlocfilehash: 9c1a5cde5a39a334d655d865c5e44a5eb0c1766a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131043"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="913cf-102">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="913cf-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="913cf-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="913cf-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="913cf-104">Extiende lógicamente la interfaz [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) para proporcionar métodos que devuelven el token de la firma de variable local de una función y que asignan los desplazamientos del lenguaje intermedio INSTRUMENTADO (IL) del generador de perfiles a los desplazamientos de Il del método original.</span><span class="sxs-lookup"><span data-stu-id="913cf-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="913cf-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="913cf-105">Methods</span></span>  
  
|<span data-ttu-id="913cf-106">Método</span><span class="sxs-lookup"><span data-stu-id="913cf-106">Method</span></span>|<span data-ttu-id="913cf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="913cf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="913cf-108">Método GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="913cf-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="913cf-109">Devuelve la correspondencia entre los desplazamientos del IL instrumentado del generador de perfiles y los desplazamientos del IL del método original para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="913cf-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="913cf-110">GetLocalVarSigToken (método)</span><span class="sxs-lookup"><span data-stu-id="913cf-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="913cf-111">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="913cf-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="913cf-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="913cf-112">Requirements</span></span>  
 <span data-ttu-id="913cf-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="913cf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="913cf-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="913cf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="913cf-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="913cf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="913cf-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="913cf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913cf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="913cf-117">See also</span></span>

- [<span data-ttu-id="913cf-118">ICorDebugILCode (interfaz)</span><span class="sxs-lookup"><span data-stu-id="913cf-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="913cf-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="913cf-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="913cf-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="913cf-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
