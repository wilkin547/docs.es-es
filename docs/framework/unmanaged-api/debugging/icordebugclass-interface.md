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
ms.openlocfilehash: 7e1ad830e728fbe764085a5808a48e4cacedc595
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133632"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="cdfb7-102">Interfaz ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="cdfb7-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="cdfb7-103">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="cdfb7-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="cdfb7-104">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cdfb7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cdfb7-105">Methods</span></span>  
  
|<span data-ttu-id="cdfb7-106">Método</span><span class="sxs-lookup"><span data-stu-id="cdfb7-106">Method</span></span>|<span data-ttu-id="cdfb7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdfb7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cdfb7-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="cdfb7-109">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="cdfb7-110">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="cdfb7-111">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="cdfb7-112">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="cdfb7-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="cdfb7-113">Obtiene el `TypeDef` token de metadatos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdfb7-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cdfb7-114">Remarks</span></span>  
 <span data-ttu-id="cdfb7-115">El `ICorDebugClass` interfaz representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="cdfb7-116">ICorDebugType (interfaz) representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="cdfb7-117">Por ejemplo, `Hashtable<K, V>` podrían estar representados por `ICorDebugClass`, mientras que `Hashtable<Int32, String>` podrían estar representados por `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="cdfb7-118">Los tipos no genéricos se representan mediante dos `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="cdfb7-119">La última interfaz se introdujo en la versión 2.0 de .NET Framework para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdfb7-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cdfb7-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdfb7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cdfb7-121">Requirements</span></span>  
 <span data-ttu-id="cdfb7-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdfb7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdfb7-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdfb7-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdfb7-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdfb7-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdfb7-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdfb7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfb7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdfb7-126">See also</span></span>

- [<span data-ttu-id="cdfb7-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cdfb7-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
