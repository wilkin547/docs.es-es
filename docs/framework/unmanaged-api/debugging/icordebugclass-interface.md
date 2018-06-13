---
title: ICorDebugClass Interfaz1
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
ms.openlocfilehash: bec35babec96da5ca5d527b19f853b4ce1c384e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406941"
---
# <a name="icordebugclass-interface1"></a><span data-ttu-id="bb019-102">ICorDebugClass Interfaz1</span><span class="sxs-lookup"><span data-stu-id="bb019-102">ICorDebugClass Interface1</span></span>
<span data-ttu-id="bb019-103">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="bb019-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="bb019-104">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="bb019-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb019-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bb019-105">Methods</span></span>  
  
|<span data-ttu-id="bb019-106">Método</span><span class="sxs-lookup"><span data-stu-id="bb019-106">Method</span></span>|<span data-ttu-id="bb019-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb019-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb019-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="bb019-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="bb019-109">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="bb019-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="bb019-110">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="bb019-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="bb019-111">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="bb019-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="bb019-112">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="bb019-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="bb019-113">Obtiene el `TypeDef` símbolo (token) de metadatos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="bb019-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb019-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb019-114">Remarks</span></span>  
 <span data-ttu-id="bb019-115">El `ICorDebugClass` interfaz representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="bb019-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="bb019-116">ICorDebugType (interfaz) representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="bb019-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="bb019-117">Por ejemplo, `Hashtable<K, V>` estaría representado por `ICorDebugClass`, mientras que `Hashtable<Int32, String>` estaría representado por `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="bb019-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="bb019-118">Los tipos no genéricos se representan mediante dos `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="bb019-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="bb019-119">La última interfaz se introdujo en la versión 2.0 de .NET Framework para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="bb019-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb019-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="bb019-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb019-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb019-121">Requirements</span></span>  
 <span data-ttu-id="bb019-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb019-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb019-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb019-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb019-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb019-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb019-125">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb019-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb019-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb019-126">See Also</span></span>  
 [<span data-ttu-id="bb019-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bb019-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
