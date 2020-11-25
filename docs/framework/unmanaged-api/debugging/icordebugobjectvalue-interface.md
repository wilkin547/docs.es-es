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
ms.openlocfilehash: 2a5a618491bf2c624669728d97a690cca315bff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724681"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="de0d4-102">Interfaz ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="de0d4-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="de0d4-103">Subclase de "ICorDebugValue" que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="de0d4-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de0d4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="de0d4-104">Methods</span></span>  
  
|<span data-ttu-id="de0d4-105">Método</span><span class="sxs-lookup"><span data-stu-id="de0d4-105">Method</span></span>|<span data-ttu-id="de0d4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="de0d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de0d4-107">Método GetClass</span><span class="sxs-lookup"><span data-stu-id="de0d4-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="de0d4-108">Obtiene un puntero de interfaz al Common Language Runtime (CLR) <xref:System.Type> del objeto al que `ICorDebugObjectValue` hace referencia.</span><span class="sxs-lookup"><span data-stu-id="de0d4-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="de0d4-109">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="de0d4-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="de0d4-110">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="de0d4-110">Not implemented.</span></span>|  
|[<span data-ttu-id="de0d4-111">Método GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="de0d4-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="de0d4-112">Obtiene un puntero de interfaz a un [ICorDebugValue](icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="de0d4-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="de0d4-113">Método GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="de0d4-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="de0d4-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="de0d4-114">Obsolete.</span></span> <span data-ttu-id="de0d4-115">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="de0d4-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="de0d4-116">Método GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="de0d4-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="de0d4-117">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="de0d4-117">Not implemented.</span></span>|  
|[<span data-ttu-id="de0d4-118">Método IsValueClass</span><span class="sxs-lookup"><span data-stu-id="de0d4-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="de0d4-119">Obtiene un valor que indica si el objeto al que hace referencia este objeto `ICorDebugObjectValue` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="de0d4-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="de0d4-120">Método SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="de0d4-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="de0d4-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="de0d4-121">Obsolete.</span></span> <span data-ttu-id="de0d4-122">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="de0d4-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de0d4-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de0d4-123">Remarks</span></span>  

 <span data-ttu-id="de0d4-124">Un `ICorDebugObjectValue` sigue siendo válido hasta que continúe el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="de0d4-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de0d4-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="de0d4-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de0d4-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de0d4-126">Requirements</span></span>  

 <span data-ttu-id="de0d4-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de0d4-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de0d4-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de0d4-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de0d4-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de0d4-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de0d4-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de0d4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de0d4-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de0d4-131">See also</span></span>

- [<span data-ttu-id="de0d4-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="de0d4-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
