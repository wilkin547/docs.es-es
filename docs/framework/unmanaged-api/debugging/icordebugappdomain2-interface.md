---
title: ICorDebugAppDomain2 Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c811107fcf32696aee17810af06ac0b2ddc9102d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="adde4-102">ICorDebugAppDomain2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="adde4-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="adde4-103">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="adde4-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="adde4-104">Esta interfaz es una extensión de ICorDebugAppDomain (interfaz).</span><span class="sxs-lookup"><span data-stu-id="adde4-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="adde4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="adde4-105">Methods</span></span>  
  
|<span data-ttu-id="adde4-106">Método</span><span class="sxs-lookup"><span data-stu-id="adde4-106">Method</span></span>|<span data-ttu-id="adde4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="adde4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="adde4-108">GetArrayOrPointerType (método)</span><span class="sxs-lookup"><span data-stu-id="adde4-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="adde4-109">Obtiene una matriz del tipo especificado, o un puntero o referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="adde4-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="adde4-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="adde4-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="adde4-111">Obtiene un puntero a una función que tiene una firma dada.</span><span class="sxs-lookup"><span data-stu-id="adde4-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adde4-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="adde4-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adde4-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="adde4-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adde4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="adde4-114">Requirements</span></span>  
 <span data-ttu-id="adde4-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adde4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adde4-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adde4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adde4-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adde4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adde4-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adde4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adde4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="adde4-119">See Also</span></span>  
 [<span data-ttu-id="adde4-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="adde4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
