---
title: Interfaz ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5099af23a2b706694bfcb655d295607c97ea8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969281"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="f20d1-102">Interfaz ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="f20d1-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="f20d1-103">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="f20d1-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="f20d1-104">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="f20d1-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f20d1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f20d1-105">Methods</span></span>  
  
|<span data-ttu-id="f20d1-106">Método</span><span class="sxs-lookup"><span data-stu-id="f20d1-106">Method</span></span>|<span data-ttu-id="f20d1-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f20d1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f20d1-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="f20d1-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="f20d1-109">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="f20d1-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="f20d1-110">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="f20d1-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="f20d1-111">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="f20d1-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="f20d1-112">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="f20d1-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="f20d1-113">Obtiene el `TypeDef` símbolo (token) de metadatos de esta clase.</span><span class="sxs-lookup"><span data-stu-id="f20d1-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f20d1-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f20d1-114">Remarks</span></span>  
 <span data-ttu-id="f20d1-115">La `ICorDebugClass` interfaz representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="f20d1-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="f20d1-116">La interfaz ICorDebugType representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="f20d1-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="f20d1-117">Por ejemplo, `Hashtable<K, V>` se representará `ICorDebugClass`mediante, `Hashtable<Int32, String>` mientras que se representaría mediante `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="f20d1-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="f20d1-118">Los `ICorDebugClass` tipos no genéricos están representados `ICorDebugType`por y.</span><span class="sxs-lookup"><span data-stu-id="f20d1-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="f20d1-119">La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="f20d1-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f20d1-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f20d1-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f20d1-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f20d1-121">Requirements</span></span>  
 <span data-ttu-id="f20d1-122">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f20d1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f20d1-123">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f20d1-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f20d1-124">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f20d1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f20d1-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f20d1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f20d1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f20d1-126">See also</span></span>

- [<span data-ttu-id="f20d1-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f20d1-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
