---
description: 'Más información acerca de: ICorDebugObjectValue (interfaz)'
title: Interfaz ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: a2af438bbb4c2f56eb1a72151e339b6b0a978eec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794780"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="ba9cc-103">Interfaz ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="ba9cc-103">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="ba9cc-104">Subclase de "ICorDebugValue" que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-104">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba9cc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ba9cc-105">Methods</span></span>  
  
|<span data-ttu-id="ba9cc-106">Método</span><span class="sxs-lookup"><span data-stu-id="ba9cc-106">Method</span></span>|<span data-ttu-id="ba9cc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba9cc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba9cc-108">Método GetClass</span><span class="sxs-lookup"><span data-stu-id="ba9cc-108">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="ba9cc-109">Obtiene un puntero de interfaz al Common Language Runtime (CLR) <xref:System.Type> del objeto al que `ICorDebugObjectValue` hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-109">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="ba9cc-110">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="ba9cc-110">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="ba9cc-111">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-111">Not implemented.</span></span>|  
|[<span data-ttu-id="ba9cc-112">Método GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="ba9cc-112">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="ba9cc-113">Obtiene un puntero de interfaz a un [ICorDebugValue](icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-113">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="ba9cc-114">Método GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="ba9cc-114">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="ba9cc-115">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-115">Obsolete.</span></span> <span data-ttu-id="ba9cc-116">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-116">Do not call this method.</span></span>|  
|[<span data-ttu-id="ba9cc-117">Método GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="ba9cc-117">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="ba9cc-118">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-118">Not implemented.</span></span>|  
|[<span data-ttu-id="ba9cc-119">Método IsValueClass</span><span class="sxs-lookup"><span data-stu-id="ba9cc-119">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="ba9cc-120">Obtiene un valor que indica si el objeto al que hace referencia este objeto `ICorDebugObjectValue` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-120">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="ba9cc-121">Método SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="ba9cc-121">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="ba9cc-122">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-122">Obsolete.</span></span> <span data-ttu-id="ba9cc-123">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-123">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba9cc-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba9cc-124">Remarks</span></span>  

 <span data-ttu-id="ba9cc-125">Un `ICorDebugObjectValue` sigue siendo válido hasta que continúe el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-125">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba9cc-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ba9cc-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba9cc-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba9cc-127">Requirements</span></span>  

 <span data-ttu-id="ba9cc-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba9cc-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba9cc-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba9cc-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba9cc-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba9cc-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba9cc-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba9cc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba9cc-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba9cc-132">See also</span></span>

- [<span data-ttu-id="ba9cc-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ba9cc-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
