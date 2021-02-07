---
description: 'Más información acerca de: ICorDebugClass (interfaz)'
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
ms.openlocfilehash: 5ded26a8b3a98bd273bbfe1bfa9efd1bb70d5595
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711510"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="7bc72-103">Interfaz ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="7bc72-103">ICorDebugClass Interface</span></span>

<span data-ttu-id="7bc72-104">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="7bc72-104">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="7bc72-105">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="7bc72-105">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7bc72-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="7bc72-106">Methods</span></span>  
  
|<span data-ttu-id="7bc72-107">Método</span><span class="sxs-lookup"><span data-stu-id="7bc72-107">Method</span></span>|<span data-ttu-id="7bc72-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7bc72-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7bc72-109">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="7bc72-109">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="7bc72-110">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="7bc72-110">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="7bc72-111">Método GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="7bc72-111">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="7bc72-112">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="7bc72-112">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="7bc72-113">GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="7bc72-113">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="7bc72-114">Obtiene el `TypeDef` símbolo (token) de metadatos de esta clase.</span><span class="sxs-lookup"><span data-stu-id="7bc72-114">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bc72-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7bc72-115">Remarks</span></span>  

 <span data-ttu-id="7bc72-116">La `ICorDebugClass` interfaz representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="7bc72-116">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="7bc72-117">La interfaz ICorDebugType representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="7bc72-117">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="7bc72-118">Por ejemplo, `Hashtable<K, V>` se representará mediante `ICorDebugClass` , mientras que `Hashtable<Int32, String>` se representaría mediante `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="7bc72-118">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="7bc72-119">Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="7bc72-119">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="7bc72-120">La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="7bc72-120">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bc72-121">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7bc72-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bc72-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bc72-122">Requirements</span></span>  

 <span data-ttu-id="7bc72-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bc72-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bc72-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bc72-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bc72-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bc72-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bc72-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bc72-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc72-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bc72-127">See also</span></span>

- [<span data-ttu-id="7bc72-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7bc72-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
