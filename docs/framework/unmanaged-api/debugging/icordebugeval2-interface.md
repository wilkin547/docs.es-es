---
title: ICorDebugEval2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2
helpviewer_keywords:
- ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: fce34531-2687-406d-9131-d6ad94f2ce0e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4315c9f5296e8c3ffc9d8241b929c71c2448db6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965870"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="cb766-102">ICorDebugEval2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb766-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="cb766-103">Extiende "ICorDebugEval" para proporcionar compatibilidad con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="cb766-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb766-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cb766-104">Methods</span></span>  
  
|<span data-ttu-id="cb766-105">Método</span><span class="sxs-lookup"><span data-stu-id="cb766-105">Method</span></span>|<span data-ttu-id="cb766-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb766-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb766-107">CallParameterizedFunction (método)</span><span class="sxs-lookup"><span data-stu-id="cb766-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="cb766-108">Configura una llamada a la especificada "ICorDebugFunction", que se puede anidar dentro de un tipo cuyo constructor toma parámetros de tipo, o puede tomar parámetros de tipo por sí misma.</span><span class="sxs-lookup"><span data-stu-id="cb766-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="cb766-109">CreateValueForType (método)</span><span class="sxs-lookup"><span data-stu-id="cb766-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="cb766-110">Obtiene un puntero a un nuevo "ICorDebugValue" del tipo especificado, con un valor inicial de cero o null.</span><span class="sxs-lookup"><span data-stu-id="cb766-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="cb766-111">NewParameterizedArray (método)</span><span class="sxs-lookup"><span data-stu-id="cb766-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="cb766-112">Asigna una nueva matriz del tipo de elemento especificado y las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="cb766-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="cb766-113">NewParameterizedObject (método)</span><span class="sxs-lookup"><span data-stu-id="cb766-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="cb766-114">Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.</span><span class="sxs-lookup"><span data-stu-id="cb766-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="cb766-115">NewParameterizedObjectNoConstructor (método)</span><span class="sxs-lookup"><span data-stu-id="cb766-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="cb766-116">Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor</span><span class="sxs-lookup"><span data-stu-id="cb766-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="cb766-117">NewStringWithLength (método)</span><span class="sxs-lookup"><span data-stu-id="cb766-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="cb766-118">Crea una nueva cadena de la longitud especificada con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="cb766-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="cb766-119">RudeAbort (método)</span><span class="sxs-lookup"><span data-stu-id="cb766-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="cb766-120">Anula el cálculo que `ICorDebugEval2` está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="cb766-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb766-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb766-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb766-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cb766-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb766-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb766-123">Requirements</span></span>  
 <span data-ttu-id="cb766-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb766-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb766-125">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb766-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb766-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb766-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb766-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb766-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb766-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb766-128">See also</span></span>
- [<span data-ttu-id="cb766-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cb766-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
