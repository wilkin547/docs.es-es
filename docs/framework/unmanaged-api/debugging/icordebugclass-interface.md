---
title: ICorDebugClass (Interfaz1)
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
ms.openlocfilehash: d12d952fe540b2ec36d058ae2100f0cf5c8e6bcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710232"
---
# <a name="icordebugclass-interface1"></a><span data-ttu-id="4f60e-102">ICorDebugClass (Interfaz1)</span><span class="sxs-lookup"><span data-stu-id="4f60e-102">ICorDebugClass Interface1</span></span>
<span data-ttu-id="4f60e-103">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="4f60e-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="4f60e-104">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="4f60e-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f60e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4f60e-105">Methods</span></span>  
  
|<span data-ttu-id="4f60e-106">Método</span><span class="sxs-lookup"><span data-stu-id="4f60e-106">Method</span></span>|<span data-ttu-id="4f60e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f60e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f60e-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="4f60e-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="4f60e-109">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="4f60e-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="4f60e-110">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="4f60e-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="4f60e-111">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="4f60e-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="4f60e-112">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="4f60e-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="4f60e-113">Obtiene el `TypeDef` token de metadatos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="4f60e-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f60e-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f60e-114">Remarks</span></span>  
 <span data-ttu-id="4f60e-115">El `ICorDebugClass` interfaz representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="4f60e-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="4f60e-116">ICorDebugType (interfaz) representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="4f60e-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="4f60e-117">Por ejemplo, `Hashtable<K, V>` podrían estar representados por `ICorDebugClass`, mientras que `Hashtable<Int32, String>` podrían estar representados por `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="4f60e-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="4f60e-118">Los tipos no genéricos se representan mediante dos `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="4f60e-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="4f60e-119">La última interfaz se introdujo en la versión 2.0 de .NET Framework para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="4f60e-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f60e-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4f60e-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f60e-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f60e-121">Requirements</span></span>  
 <span data-ttu-id="4f60e-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f60e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f60e-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f60e-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f60e-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f60e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f60e-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f60e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f60e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f60e-126">See also</span></span>
- [<span data-ttu-id="4f60e-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4f60e-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
