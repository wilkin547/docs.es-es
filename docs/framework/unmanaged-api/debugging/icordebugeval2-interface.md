---
title: Interfaz ICorDebugEval2
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
ms.openlocfilehash: 3767368c9da8c97cd081787c0945a15552a1da46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092674"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="5c77c-102">Interfaz ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="5c77c-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="5c77c-103">Extiende "ICorDebugEval" para proporcionar compatibilidad con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="5c77c-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c77c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c77c-104">Methods</span></span>  
  
|<span data-ttu-id="5c77c-105">Método</span><span class="sxs-lookup"><span data-stu-id="5c77c-105">Method</span></span>|<span data-ttu-id="5c77c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c77c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c77c-107">Método CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="5c77c-107">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="5c77c-108">Configura una llamada a la especificada "ICorDebugFunction", que se puede anidar dentro de un tipo cuyo constructor toma parámetros de tipo, o puede tomar parámetros de tipo por sí misma.</span><span class="sxs-lookup"><span data-stu-id="5c77c-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="5c77c-109">Método CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="5c77c-109">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="5c77c-110">Obtiene un puntero a un nuevo "ICorDebugValue" del tipo especificado, con un valor inicial de cero o null.</span><span class="sxs-lookup"><span data-stu-id="5c77c-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="5c77c-111">Método NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="5c77c-111">NewParameterizedArray Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="5c77c-112">Asigna una nueva matriz del tipo de elemento especificado y las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5c77c-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="5c77c-113">Método NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="5c77c-113">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="5c77c-114">Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.</span><span class="sxs-lookup"><span data-stu-id="5c77c-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="5c77c-115">Método NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="5c77c-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="5c77c-116">Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor</span><span class="sxs-lookup"><span data-stu-id="5c77c-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="5c77c-117">Método NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="5c77c-117">NewStringWithLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="5c77c-118">Crea una nueva cadena de la longitud especificada con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="5c77c-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="5c77c-119">Método RudeAbort</span><span class="sxs-lookup"><span data-stu-id="5c77c-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-rudeabort-method.md)|<span data-ttu-id="5c77c-120">Anula el cálculo que `ICorDebugEval2` está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="5c77c-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c77c-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c77c-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c77c-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5c77c-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c77c-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c77c-123">Requirements</span></span>  
 <span data-ttu-id="5c77c-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c77c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c77c-125">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c77c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c77c-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c77c-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5c77c-127">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c77c-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c77c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c77c-128">See also</span></span>

- [<span data-ttu-id="5c77c-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5c77c-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
