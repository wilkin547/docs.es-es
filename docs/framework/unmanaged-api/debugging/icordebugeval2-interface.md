---
description: 'Más información acerca de: interfaz ICorDebugEval2'
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
ms.openlocfilehash: 2c279335bdd30b8dc2698f348d9537443b236a45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693764"
---
# <a name="icordebugeval2-interface"></a><span data-ttu-id="8bf4e-103">Interfaz ICorDebugEval2</span><span class="sxs-lookup"><span data-stu-id="8bf4e-103">ICorDebugEval2 Interface</span></span>

<span data-ttu-id="8bf4e-104">Extiende "ICorDebugEval" para proporcionar compatibilidad con los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-104">Extends "ICorDebugEval" to provide support for generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8bf4e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8bf4e-105">Methods</span></span>  
  
|<span data-ttu-id="8bf4e-106">Método</span><span class="sxs-lookup"><span data-stu-id="8bf4e-106">Method</span></span>|<span data-ttu-id="8bf4e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bf4e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8bf4e-108">Método CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="8bf4e-108">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)|<span data-ttu-id="8bf4e-109">Configura una llamada a la instrucción "ICorDebugFunction" especificada, que puede estar anidada dentro de un tipo cuyo constructor toma parámetros de tipo, o bien puede tomar parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-109">Sets up a call to the specified "ICorDebugFunction", which can be nested inside a type whose constructor takes type parameters, or can itself take type parameters.</span></span>|  
|[<span data-ttu-id="8bf4e-110">Método CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="8bf4e-110">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)|<span data-ttu-id="8bf4e-111">Obtiene un puntero a una nueva expresión "ICorDebugValue" del tipo especificado, con un valor inicial de null o cero.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-111">Gets a pointer to a new "ICorDebugValue" of the specified type, with an initial value of null or zero.</span></span>|  
|[<span data-ttu-id="8bf4e-112">Método NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="8bf4e-112">NewParameterizedArray Method</span></span>](icordebugeval2-newparameterizedarray-method.md)|<span data-ttu-id="8bf4e-113">Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-113">Allocates a new array of the specified element type and dimensions.</span></span>|  
|[<span data-ttu-id="8bf4e-114">Método NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="8bf4e-114">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)|<span data-ttu-id="8bf4e-115">Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-115">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>|  
|[<span data-ttu-id="8bf4e-116">Método NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="8bf4e-116">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)|<span data-ttu-id="8bf4e-117">Crea una instancia de un nuevo objeto de tipo parametrizado de la clase especificada sin intentar llamar a un método de constructor.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-117">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method</span></span>|  
|[<span data-ttu-id="8bf4e-118">Método NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="8bf4e-118">NewStringWithLength Method</span></span>](icordebugeval2-newstringwithlength-method.md)|<span data-ttu-id="8bf4e-119">Crea una nueva cadena de la longitud especificada con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-119">Creates a new string of the specified length with the specified contents.</span></span>|  
|[<span data-ttu-id="8bf4e-120">RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="8bf4e-120">RudeAbort Method</span></span>](icordebugeval2-rudeabort-method.md)|<span data-ttu-id="8bf4e-121">Anula el cálculo que `ICorDebugEval2` está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-121">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bf4e-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8bf4e-122">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8bf4e-123">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8bf4e-123">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bf4e-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bf4e-124">Requirements</span></span>  

 <span data-ttu-id="8bf4e-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bf4e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf4e-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bf4e-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bf4e-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bf4e-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bf4e-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf4e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf4e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bf4e-129">See also</span></span>

- [<span data-ttu-id="8bf4e-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8bf4e-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
