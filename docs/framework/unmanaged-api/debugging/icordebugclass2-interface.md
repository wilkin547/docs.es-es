---
description: 'Más información acerca de: interfaz ICorDebugClass2'
title: Interfaz ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: 80aa8e59ccc774141e7fcea130d1fc6a38fa37da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711480"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="ba058-103">Interfaz ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="ba058-103">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="ba058-104">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="ba058-104">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="ba058-105">Esta interfaz extiende [ICorDebugClass](icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ba058-105">This interface extends [ICorDebugClass](icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba058-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="ba058-106">Methods</span></span>  
  
|<span data-ttu-id="ba058-107">Método</span><span class="sxs-lookup"><span data-stu-id="ba058-107">Method</span></span>|<span data-ttu-id="ba058-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba058-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba058-109">Método GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="ba058-109">GetParameterizedType Method</span></span>](icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="ba058-110">Obtiene la declaración de tipos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="ba058-110">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="ba058-111">SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="ba058-111">SetJMCStatus Method</span></span>](icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="ba058-112">Para cada método de esta clase, establece un valor que indica si el método es código definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ba058-112">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba058-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba058-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba058-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ba058-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba058-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba058-115">Requirements</span></span>  

 <span data-ttu-id="ba058-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba058-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba058-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba058-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba058-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba058-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba058-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba058-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba058-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba058-120">See also</span></span>

- [<span data-ttu-id="ba058-121">Interfaz ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="ba058-121">ICorDebugClass Interface</span></span>](icordebugclass-interface.md)
- [<span data-ttu-id="ba058-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ba058-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
