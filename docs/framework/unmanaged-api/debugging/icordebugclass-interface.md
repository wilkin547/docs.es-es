---
title: ICorDebugClass (Interfaz)
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
ms.openlocfilehash: 5714597b5e5ca2936aad53217ae934684e75585c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125749"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="f7b7d-102">ICorDebugClass (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7b7d-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="f7b7d-103">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="f7b7d-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="f7b7d-104">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7b7d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f7b7d-105">Methods</span></span>  
  
|<span data-ttu-id="f7b7d-106">Método</span><span class="sxs-lookup"><span data-stu-id="f7b7d-106">Method</span></span>|<span data-ttu-id="f7b7d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7b7d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7b7d-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="f7b7d-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="f7b7d-109">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="f7b7d-110">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="f7b7d-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="f7b7d-111">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="f7b7d-112">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="f7b7d-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="f7b7d-113">Obtiene el token de metadatos de `TypeDef` para esta clase.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7b7d-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7b7d-114">Remarks</span></span>  
 <span data-ttu-id="f7b7d-115">La interfaz `ICorDebugClass` representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="f7b7d-116">La interfaz ICorDebugType representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="f7b7d-117">Por ejemplo, `Hashtable<K, V>` se representará mediante `ICorDebugClass`, mientras que `Hashtable<Int32, String>` se representará mediante `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="f7b7d-118">Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="f7b7d-119">La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7b7d-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f7b7d-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b7d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7b7d-121">Requirements</span></span>  
 <span data-ttu-id="f7b7d-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b7d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b7d-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7b7d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7b7d-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7b7d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7b7d-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b7d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b7d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7b7d-126">See also</span></span>

- [<span data-ttu-id="f7b7d-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f7b7d-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
