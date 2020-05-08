---
title: Interfaz ICorDebugAppDomain2
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
ms.openlocfilehash: 1643d91f373ff233540026440ee21aa4c146f3e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895135"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="ad131-102">Interfaz ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="ad131-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="ad131-103">Proporciona métodos para trabajar con matrices, punteros, punteros de función y tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="ad131-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="ad131-104">Esta interfaz es una extensión de la interfaz ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="ad131-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad131-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad131-105">Methods</span></span>  
  
|<span data-ttu-id="ad131-106">Método</span><span class="sxs-lookup"><span data-stu-id="ad131-106">Method</span></span>|<span data-ttu-id="ad131-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad131-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad131-108">Método GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="ad131-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="ad131-109">Obtiene una matriz del tipo especificado, o un puntero o una referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ad131-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="ad131-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="ad131-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="ad131-111">Obtiene un puntero a una función que tiene una firma especificada.</span><span class="sxs-lookup"><span data-stu-id="ad131-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad131-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad131-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad131-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ad131-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad131-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad131-114">Requirements</span></span>  
 <span data-ttu-id="ad131-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad131-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad131-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad131-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad131-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad131-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad131-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad131-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad131-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ad131-119">See also</span></span>

- [<span data-ttu-id="ad131-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ad131-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
