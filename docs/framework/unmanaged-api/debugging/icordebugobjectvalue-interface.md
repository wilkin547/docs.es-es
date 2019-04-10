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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0ac91681313b60ebfcaf725dcc2e0d6547e3c1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222619"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="a4f0b-102">Interfaz ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="a4f0b-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="a4f0b-103">Una subclase de "ICorDebugValue" que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4f0b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a4f0b-104">Methods</span></span>  
  
|<span data-ttu-id="a4f0b-105">Método</span><span class="sxs-lookup"><span data-stu-id="a4f0b-105">Method</span></span>|<span data-ttu-id="a4f0b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4f0b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4f0b-107">Método GetClass</span><span class="sxs-lookup"><span data-stu-id="a4f0b-107">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="a4f0b-108">Obtiene un puntero de interfaz a common language runtime (CLR) <xref:System.Type> del objeto que este `ICorDebugObjectValue` referencias.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="a4f0b-109">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="a4f0b-109">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="a4f0b-110">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-110">Not implemented.</span></span>|  
|[<span data-ttu-id="a4f0b-111">Método GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="a4f0b-111">GetFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="a4f0b-112">Obtiene un puntero de interfaz a un [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) que representa el valor del campo especificado de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-112">Gets an interface pointer to an [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="a4f0b-113">Método GetManagedCopy</span><span class="sxs-lookup"><span data-stu-id="a4f0b-113">GetManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="a4f0b-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-114">Obsolete.</span></span> <span data-ttu-id="a4f0b-115">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="a4f0b-116">Método GetVirtualMethod</span><span class="sxs-lookup"><span data-stu-id="a4f0b-116">GetVirtualMethod Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="a4f0b-117">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-117">Not implemented.</span></span>|  
|[<span data-ttu-id="a4f0b-118">Método IsValueClass</span><span class="sxs-lookup"><span data-stu-id="a4f0b-118">IsValueClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="a4f0b-119">Obtiene un valor que indica si el objeto que hace referencia esta `ICorDebugObjectValue` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="a4f0b-120">Método SetFromManagedCopy</span><span class="sxs-lookup"><span data-stu-id="a4f0b-120">SetFromManagedCopy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="a4f0b-121">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-121">Obsolete.</span></span> <span data-ttu-id="a4f0b-122">No llame a este método.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4f0b-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4f0b-123">Remarks</span></span>  
 <span data-ttu-id="a4f0b-124">Un `ICorDebugObjectValue` sigue siendo válida hasta que se continúa el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4f0b-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a4f0b-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4f0b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4f0b-126">Requirements</span></span>  
 <span data-ttu-id="a4f0b-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4f0b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4f0b-128">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4f0b-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4f0b-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4f0b-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4f0b-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a4f0b-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4f0b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4f0b-131">See also</span></span>

- [<span data-ttu-id="a4f0b-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a4f0b-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
