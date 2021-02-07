---
description: 'Más información acerca de: interfaz ICorDebugAppDomain2'
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
ms.openlocfilehash: 2f2fcc4166a0c825abaa04392f9905d17e286803
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754194"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="d6d69-103">Interfaz ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="d6d69-103">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="d6d69-104">Proporciona métodos para trabajar con matrices, punteros, punteros de función y tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="d6d69-104">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="d6d69-105">Esta interfaz es una extensión de la interfaz ICorDebugAppDomain.</span><span class="sxs-lookup"><span data-stu-id="d6d69-105">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6d69-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="d6d69-106">Methods</span></span>  
  
|<span data-ttu-id="d6d69-107">Método</span><span class="sxs-lookup"><span data-stu-id="d6d69-107">Method</span></span>|<span data-ttu-id="d6d69-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6d69-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6d69-109">Método GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="d6d69-109">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="d6d69-110">Obtiene una matriz del tipo especificado, o un puntero o una referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="d6d69-110">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="d6d69-111">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="d6d69-111">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="d6d69-112">Obtiene un puntero a una función que tiene una firma especificada.</span><span class="sxs-lookup"><span data-stu-id="d6d69-112">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6d69-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6d69-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6d69-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d6d69-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6d69-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6d69-115">Requirements</span></span>  

 <span data-ttu-id="d6d69-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6d69-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6d69-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6d69-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6d69-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6d69-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6d69-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6d69-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d69-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6d69-120">See also</span></span>

- [<span data-ttu-id="d6d69-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d6d69-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
