---
title: ICorDebugClass Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass
helpviewer_keywords: ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79e93a44f2cc532286a7e9b01fa32292a4e1c69a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass-interface1"></a><span data-ttu-id="ecddc-102">ICorDebugClass Interfaz1</span><span class="sxs-lookup"><span data-stu-id="ecddc-102">ICorDebugClass Interface1</span></span>
<span data-ttu-id="ecddc-103">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="ecddc-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="ecddc-104">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="ecddc-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ecddc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ecddc-105">Methods</span></span>  
  
|<span data-ttu-id="ecddc-106">Método</span><span class="sxs-lookup"><span data-stu-id="ecddc-106">Method</span></span>|<span data-ttu-id="ecddc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecddc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ecddc-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="ecddc-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="ecddc-109">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="ecddc-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="ecddc-110">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="ecddc-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="ecddc-111">Obtiene el valor del campo estático especificado.</span><span class="sxs-lookup"><span data-stu-id="ecddc-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="ecddc-112">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="ecddc-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="ecddc-113">Obtiene el `TypeDef` símbolo (token) de metadatos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="ecddc-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecddc-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ecddc-114">Remarks</span></span>  
 <span data-ttu-id="ecddc-115">El `ICorDebugClass` interfaz representa un tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="ecddc-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="ecddc-116">ICorDebugType (interfaz) representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="ecddc-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="ecddc-117">Por ejemplo, `Hashtable<K, V>` estaría representado por `ICorDebugClass`, mientras que `Hashtable<Int32, String>` estaría representado por `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="ecddc-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="ecddc-118">Los tipos no genéricos se representan mediante dos `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="ecddc-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="ecddc-119">La última interfaz se introdujo en la versión 2.0 de .NET Framework para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="ecddc-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecddc-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ecddc-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecddc-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecddc-121">Requirements</span></span>  
 <span data-ttu-id="ecddc-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecddc-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecddc-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecddc-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecddc-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecddc-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecddc-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecddc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecddc-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecddc-126">See Also</span></span>  
 [<span data-ttu-id="ecddc-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ecddc-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
