---
title: ICorDebugObjectValue (Interfaz1)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd991049c159b96a0f0717b31d6a2834b250f70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631998"
---
# <a name="icordebugobjectvalue-interface1"></a><span data-ttu-id="8f697-102">ICorDebugObjectValue (Interfaz1)</span><span class="sxs-lookup"><span data-stu-id="8f697-102">ICorDebugObjectValue Interface1</span></span>
<span data-ttu-id="8f697-103">Una subclase de "ICorDebugValue" que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="8f697-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f697-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8f697-104">Methods</span></span>  
  
|<span data-ttu-id="8f697-105">Método</span><span class="sxs-lookup"><span data-stu-id="8f697-105">Method</span></span>|<span data-ttu-id="8f697-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f697-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f697-107">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="8f697-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="8f697-108">Obtiene un puntero de interfaz a common language runtime (CLR) <xref:System.Type> del objeto que este `ICorDebugObjectValue` referencias.</span><span class="sxs-lookup"><span data-stu-id="8f697-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="8f697-109">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="8f697-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="8f697-110">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="8f697-110">Not implemented.</span></span>|  
|[<span data-ttu-id="8f697-111">GetFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="8f697-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="8f697-112">Obtiene un puntero de interfaz a un [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="8f697-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="8f697-113">GetManagedCopy (método)</span><span class="sxs-lookup"><span data-stu-id="8f697-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="8f697-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="8f697-114">Obsolete.</span></span> <span data-ttu-id="8f697-115">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="8f697-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="8f697-116">GetVirtualMethod (método)</span><span class="sxs-lookup"><span data-stu-id="8f697-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="8f697-117">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="8f697-117">Not implemented.</span></span>|  
|[<span data-ttu-id="8f697-118">IsValueClass (método)</span><span class="sxs-lookup"><span data-stu-id="8f697-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="8f697-119">Obtiene un valor que indica si el objeto que hace referencia esta `ICorDebugObjectValue` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="8f697-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="8f697-120">SetFromManagedCopy (método)</span><span class="sxs-lookup"><span data-stu-id="8f697-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="8f697-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="8f697-121">Obsolete.</span></span> <span data-ttu-id="8f697-122">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="8f697-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f697-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f697-123">Remarks</span></span>  
 <span data-ttu-id="8f697-124">Un `ICorDebugObjectValue` sigue siendo válida hasta que se continúa el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="8f697-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f697-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8f697-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f697-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f697-126">Requirements</span></span>  
 <span data-ttu-id="8f697-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f697-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f697-128">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f697-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f697-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f697-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f697-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f697-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f697-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f697-131">See also</span></span>
- [<span data-ttu-id="8f697-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8f697-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

