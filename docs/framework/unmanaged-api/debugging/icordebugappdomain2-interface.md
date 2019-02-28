---
title: ICorDebugAppDomain2 (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82b58780472443874f2dae93c2d8568006db2e8a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978571"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="f8ecc-102">ICorDebugAppDomain2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8ecc-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="f8ecc-103">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="f8ecc-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="f8ecc-104">Esta interfaz es una extensión de ICorDebugAppDomain (interfaz).</span><span class="sxs-lookup"><span data-stu-id="f8ecc-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8ecc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f8ecc-105">Methods</span></span>  
  
|<span data-ttu-id="f8ecc-106">Método</span><span class="sxs-lookup"><span data-stu-id="f8ecc-106">Method</span></span>|<span data-ttu-id="f8ecc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8ecc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8ecc-108">GetArrayOrPointerType (método)</span><span class="sxs-lookup"><span data-stu-id="f8ecc-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="f8ecc-109">Obtiene una matriz de tipo especificado, o un puntero o referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f8ecc-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="f8ecc-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="f8ecc-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="f8ecc-111">Obtiene un puntero a una función que tiene una firma dada.</span><span class="sxs-lookup"><span data-stu-id="f8ecc-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8ecc-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8ecc-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8ecc-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f8ecc-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8ecc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8ecc-114">Requirements</span></span>  
 <span data-ttu-id="f8ecc-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8ecc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8ecc-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8ecc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8ecc-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8ecc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8ecc-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8ecc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ecc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8ecc-119">See also</span></span>
- [<span data-ttu-id="f8ecc-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f8ecc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
