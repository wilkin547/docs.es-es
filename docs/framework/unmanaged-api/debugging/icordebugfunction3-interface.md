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
ms.openlocfilehash: 71aa482cc2268da17f1376d8c305dd6a818d92d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213171"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="62bc8-102">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62bc8-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="62bc8-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="62bc8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="62bc8-104">Extiende la interfaz ICorDebugFunction de manera lógica para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="62bc8-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62bc8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="62bc8-105">Methods</span></span>  
  
|<span data-ttu-id="62bc8-106">Método</span><span class="sxs-lookup"><span data-stu-id="62bc8-106">Method</span></span>|<span data-ttu-id="62bc8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="62bc8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62bc8-108">GetActiveReJitRequestILCode (método)</span><span class="sxs-lookup"><span data-stu-id="62bc8-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="62bc8-109">Obtiene un puntero de interfaz a un [ICorDebugILCode](icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="62bc8-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62bc8-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62bc8-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62bc8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62bc8-111">Requirements</span></span>  
 <span data-ttu-id="62bc8-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62bc8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62bc8-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62bc8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62bc8-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62bc8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62bc8-115">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62bc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62bc8-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62bc8-116">See also</span></span>

- [<span data-ttu-id="62bc8-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="62bc8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="62bc8-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="62bc8-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="62bc8-119">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="62bc8-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
