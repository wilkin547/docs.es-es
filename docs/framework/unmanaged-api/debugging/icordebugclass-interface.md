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
ms.openlocfilehash: d7417e8dc193172c77d23fe3fa72c8298d802b5c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894044"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="dc39f-102">Interfaz ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="dc39f-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="dc39f-103">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="dc39f-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="dc39f-104">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="dc39f-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc39f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dc39f-105">Methods</span></span>  
  
|<span data-ttu-id="dc39f-106">Método</span><span class="sxs-lookup"><span data-stu-id="dc39f-106">Method</span></span>|<span data-ttu-id="dc39f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc39f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc39f-108">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="dc39f-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="dc39f-109">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="dc39f-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="dc39f-110">Método GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="dc39f-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="dc39f-111">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="dc39f-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="dc39f-112">GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="dc39f-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="dc39f-113">Obtiene el `TypeDef` símbolo (token) de metadatos de esta clase.</span><span class="sxs-lookup"><span data-stu-id="dc39f-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc39f-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dc39f-114">Remarks</span></span>  
 <span data-ttu-id="dc39f-115">La `ICorDebugClass` interfaz representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="dc39f-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="dc39f-116">La interfaz ICorDebugType representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="dc39f-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="dc39f-117">Por ejemplo, `Hashtable<K, V>` se representará `ICorDebugClass`mediante, `Hashtable<Int32, String>` mientras que se representaría mediante `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="dc39f-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="dc39f-118">Los `ICorDebugClass` tipos no genéricos están representados `ICorDebugType`por y.</span><span class="sxs-lookup"><span data-stu-id="dc39f-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="dc39f-119">La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="dc39f-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc39f-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="dc39f-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc39f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc39f-121">Requirements</span></span>  
 <span data-ttu-id="dc39f-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc39f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc39f-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc39f-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc39f-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc39f-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc39f-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc39f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc39f-126">Consulta también</span><span class="sxs-lookup"><span data-stu-id="dc39f-126">See also</span></span>

- [<span data-ttu-id="dc39f-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dc39f-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
