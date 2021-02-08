---
description: 'Más información acerca de: interfaz ICorDebugILCode2'
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
ms.openlocfilehash: 52e47b8cbf8f9926797e193944fd7e97b2e4dbcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791418"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="e22cb-103">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e22cb-103">ICorDebugILCode2 Interface</span></span>

<span data-ttu-id="e22cb-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="e22cb-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e22cb-105">Extiende lógicamente la interfaz [ICorDebugILCode](icordebugilcode-interface.md) para proporcionar métodos que devuelven el token de la firma de variable local de una función y que asignan los desplazamientos del lenguaje intermedio INSTRUMENTADO (IL) del generador de perfiles a los desplazamientos de Il del método original.</span><span class="sxs-lookup"><span data-stu-id="e22cb-105">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e22cb-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="e22cb-106">Methods</span></span>  
  
|<span data-ttu-id="e22cb-107">Método</span><span class="sxs-lookup"><span data-stu-id="e22cb-107">Method</span></span>|<span data-ttu-id="e22cb-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e22cb-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e22cb-109">Método GetInstrumentedILMap</span><span class="sxs-lookup"><span data-stu-id="e22cb-109">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="e22cb-110">Devuelve la correspondencia entre los desplazamientos del IL instrumentado del generador de perfiles y los desplazamientos del IL del método original para esta instancia.</span><span class="sxs-lookup"><span data-stu-id="e22cb-110">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="e22cb-111">GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="e22cb-111">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="e22cb-112">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="e22cb-112">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e22cb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e22cb-113">Requirements</span></span>  

 <span data-ttu-id="e22cb-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e22cb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e22cb-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e22cb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e22cb-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e22cb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e22cb-117">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e22cb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22cb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e22cb-118">See also</span></span>

- [<span data-ttu-id="e22cb-119">ICorDebugILCode (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e22cb-119">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="e22cb-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e22cb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e22cb-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="e22cb-121">Debugging</span></span>](index.md)
