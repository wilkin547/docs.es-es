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
ms.openlocfilehash: 090b587ef509795609250914ce8883ad96d28c18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729686"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="7eb77-102">Interfaz ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="7eb77-102">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="7eb77-103">Extiende "ICorDebugEval" para proporcionar compatibilidad con los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="7eb77-103">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7eb77-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7eb77-104">Methods</span></span>  
  
|<span data-ttu-id="7eb77-105">Método</span><span class="sxs-lookup"><span data-stu-id="7eb77-105">Method</span></span>|<span data-ttu-id="7eb77-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7eb77-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7eb77-107">Método CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="7eb77-107">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="7eb77-108">Configura una llamada a la instrucción "ICorDebugFunction" especificada, que puede estar anidada dentro de un tipo cuyo constructor toma parámetros de tipo, o bien puede tomar parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="7eb77-108">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="7eb77-109">Método CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="7eb77-109">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="7eb77-110">Obtiene un puntero a una nueva expresión "ICorDebugValue" del tipo especificado, con un valor inicial de null o cero.</span><span class="sxs-lookup"><span data-stu-id="7eb77-110">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="7eb77-111">Método NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="7eb77-111">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="7eb77-112">Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="7eb77-112">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="7eb77-113">Método NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="7eb77-113">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="7eb77-114">Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.</span><span class="sxs-lookup"><span data-stu-id="7eb77-114">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="7eb77-115">Método NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="7eb77-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="7eb77-116">Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="7eb77-116">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="7eb77-117">Método NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="7eb77-117">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="7eb77-118">Crea una nueva cadena de la longitud especificada con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="7eb77-118">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="7eb77-119">Método RudeAbort</span><span class="sxs-lookup"><span data-stu-id="7eb77-119">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="7eb77-120">Anula el cálculo que `ICorDebugEval2` está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7eb77-120">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eb77-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7eb77-121">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7eb77-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7eb77-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb77-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7eb77-123">Requirements</span></span>  

 <span data-ttu-id="7eb77-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb77-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eb77-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7eb77-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eb77-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eb77-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eb77-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb77-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb77-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7eb77-128">See also</span></span>

- [<span data-ttu-id="7eb77-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7eb77-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
