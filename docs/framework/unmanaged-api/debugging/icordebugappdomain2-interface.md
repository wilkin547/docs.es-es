---
title: ICorDebugAppDomain2 Interfaz1
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
ms.openlocfilehash: ff6ffdd733cf6e7b923d88d057d7cd230c8d8541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407120"
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="9dd78-102">ICorDebugAppDomain2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="9dd78-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="9dd78-103">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="9dd78-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="9dd78-104">Esta interfaz es una extensión de ICorDebugAppDomain (interfaz).</span><span class="sxs-lookup"><span data-stu-id="9dd78-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9dd78-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9dd78-105">Methods</span></span>  
  
|<span data-ttu-id="9dd78-106">Método</span><span class="sxs-lookup"><span data-stu-id="9dd78-106">Method</span></span>|<span data-ttu-id="9dd78-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dd78-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9dd78-108">GetArrayOrPointerType (método)</span><span class="sxs-lookup"><span data-stu-id="9dd78-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="9dd78-109">Obtiene una matriz del tipo especificado, o un puntero o referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="9dd78-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="9dd78-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="9dd78-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="9dd78-111">Obtiene un puntero a una función que tiene una firma dada.</span><span class="sxs-lookup"><span data-stu-id="9dd78-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dd78-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dd78-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9dd78-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9dd78-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dd78-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dd78-114">Requirements</span></span>  
 <span data-ttu-id="9dd78-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dd78-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dd78-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9dd78-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9dd78-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dd78-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dd78-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dd78-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd78-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dd78-119">See Also</span></span>  
 [<span data-ttu-id="9dd78-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9dd78-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
