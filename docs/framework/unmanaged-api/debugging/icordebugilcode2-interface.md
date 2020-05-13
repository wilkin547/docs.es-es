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
ms.openlocfilehash: 65995e8386b3bc686178b79d4fbb21a7c71bed3e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210337"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="d2af6-102">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2af6-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="d2af6-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="d2af6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d2af6-104">Extiende lógicamente la interfaz [ICorDebugILCode](icordebugilcode-interface.md) para proporcionar métodos que devuelven el token de la firma de variable local de una función y que asignan los desplazamientos del lenguaje intermedio INSTRUMENTADO (IL) del generador de perfiles a los desplazamientos de Il del método original.</span><span class="sxs-lookup"><span data-stu-id="d2af6-104">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2af6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d2af6-105">Methods</span></span>  
  
|<span data-ttu-id="d2af6-106">Método</span><span class="sxs-lookup"><span data-stu-id="d2af6-106">Method</span></span>|<span data-ttu-id="d2af6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2af6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2af6-108">Método GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="d2af6-108">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="d2af6-109">Devuelve la correspondencia entre los desplazamientos del IL instrumentado del generador de perfiles y los desplazamientos del IL del método original para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="d2af6-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="d2af6-110">GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="d2af6-110">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="d2af6-111">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="d2af6-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2af6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2af6-112">Requirements</span></span>  
 <span data-ttu-id="d2af6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2af6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2af6-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2af6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2af6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2af6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2af6-116">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2af6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2af6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2af6-117">See also</span></span>

- [<span data-ttu-id="d2af6-118">ICorDebugILCode (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2af6-118">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="d2af6-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d2af6-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d2af6-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="d2af6-120">Debugging</span></span>](index.md)
