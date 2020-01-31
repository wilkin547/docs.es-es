---
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
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792686"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="0572e-102">Interfaz ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="0572e-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="0572e-103">Subclase de "ICorDebugValue" que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="0572e-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0572e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0572e-104">Methods</span></span>  
  
|<span data-ttu-id="0572e-105">Método</span><span class="sxs-lookup"><span data-stu-id="0572e-105">Method</span></span>|<span data-ttu-id="0572e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0572e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0572e-107">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="0572e-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="0572e-108">Obtiene un puntero de interfaz a la <xref:System.Type> de Common Language Runtime (CLR) del objeto al que hace referencia este `ICorDebugObjectValue`.</span><span class="sxs-lookup"><span data-stu-id="0572e-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="0572e-109">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="0572e-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="0572e-110">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="0572e-110">Not implemented.</span></span>|  
|[<span data-ttu-id="0572e-111">GetFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="0572e-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="0572e-112">Obtiene un puntero de interfaz a un [ICorDebugValue](icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="0572e-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="0572e-113">GetManagedCopy (método)</span><span class="sxs-lookup"><span data-stu-id="0572e-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="0572e-114">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="0572e-114">Obsolete.</span></span> <span data-ttu-id="0572e-115">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="0572e-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="0572e-116">GetVirtualMethod (método)</span><span class="sxs-lookup"><span data-stu-id="0572e-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="0572e-117">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="0572e-117">Not implemented.</span></span>|  
|[<span data-ttu-id="0572e-118">IsValueClass (método)</span><span class="sxs-lookup"><span data-stu-id="0572e-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="0572e-119">Obtiene un valor que indica si el objeto al que hace referencia este `ICorDebugObjectValue` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="0572e-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="0572e-120">SetFromManagedCopy (método)</span><span class="sxs-lookup"><span data-stu-id="0572e-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="0572e-121">Obsoleta.</span><span class="sxs-lookup"><span data-stu-id="0572e-121">Obsolete.</span></span> <span data-ttu-id="0572e-122">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="0572e-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0572e-123">Notas</span><span class="sxs-lookup"><span data-stu-id="0572e-123">Remarks</span></span>  
 <span data-ttu-id="0572e-124">Un `ICorDebugObjectValue` sigue siendo válido hasta que se continúa el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="0572e-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0572e-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="0572e-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0572e-126">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0572e-126">Requirements</span></span>  
 <span data-ttu-id="0572e-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0572e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0572e-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0572e-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0572e-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0572e-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0572e-130">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0572e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0572e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0572e-131">See also</span></span>

- [<span data-ttu-id="0572e-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0572e-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
