---
title: "ICorDebugClass2::GetParameterizedType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.GetParameterizedType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9cbb755bd8f52482f7eece6e9d236f29cadc419
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="c8e65-102">ICorDebugClass2::GetParameterizedType (Método)</span><span class="sxs-lookup"><span data-stu-id="c8e65-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="c8e65-103">Obtiene la declaración de tipo para esta clase.</span><span class="sxs-lookup"><span data-stu-id="c8e65-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e65-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8e65-104">Syntax</span></span>  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8e65-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8e65-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="c8e65-106">[in] Un valor de la enumeración CorElementType que especifica el tipo de elemento para esta clase: establezca este valor en ELEMENT_TYPE_VALUETYPE si ICorDebugClass2 representa un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="c8e65-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="c8e65-107">Establezca este valor en ELEMENT_TYPE_CLASS si este `ICorDebugClass2` representa un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="c8e65-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="c8e65-108">[in] El número de parámetros de tipo, si el tipo es genérico.</span><span class="sxs-lookup"><span data-stu-id="c8e65-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="c8e65-109">El número de parámetros de tipo (si existe) debe coincidir con el número necesario por la clase.</span><span class="sxs-lookup"><span data-stu-id="c8e65-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="c8e65-110">[in] Una matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="c8e65-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="c8e65-111">Si la clase es no genérica, este valor es null.</span><span class="sxs-lookup"><span data-stu-id="c8e65-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="c8e65-112">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa la declaración de tipos.</span><span class="sxs-lookup"><span data-stu-id="c8e65-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="c8e65-113">Este objeto es equivalente a un <xref:System.Type> objeto en código administrado.</span><span class="sxs-lookup"><span data-stu-id="c8e65-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8e65-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8e65-114">Remarks</span></span>  
 <span data-ttu-id="c8e65-115">Si la clase es no genérica, es decir, si no tiene ningún parámetro de tipo, `GetParameterizedType` simplemente obtiene el objeto de tipo en tiempo de ejecución correspondiente a la clase.</span><span class="sxs-lookup"><span data-stu-id="c8e65-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="c8e65-116">El `elementType` parámetro debe establecerse en el tipo de elemento correcto para la clase: ELEMENT_TYPE_VALUETYPE si la clase es un tipo de valor; en caso contrario, ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="c8e65-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="c8e65-117">Si la clase acepta parámetros de tipo (por ejemplo, `ArrayList<T>`), puede usar `GetParameterizedType` para construir un objeto de tipo para una instancia de un tipo como `ArrayList<int>`.</span><span class="sxs-lookup"><span data-stu-id="c8e65-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="c8e65-118">Información general</span><span class="sxs-lookup"><span data-stu-id="c8e65-118">Background Information</span></span>  
 <span data-ttu-id="c8e65-119">En las versiones 1.0 y 1.1 de .NET Framework, todos los tipos en los metadatos pudieron asignarse directamente a un tipo en el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c8e65-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="c8e65-120">Por lo tanto, un tipo de metadatos y un tipo en tiempo de ejecución tenían una única representación de los procesos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c8e65-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="c8e65-121">Sin embargo, un tipo genérico en los metadatos puede asignarse a muchas de las distintas instancias del tipo en el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c8e65-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="c8e65-122">Por ejemplo, el tipo de metadatos `SortedList<K,V>` puede asignar a `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c8e65-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="c8e65-123">Por lo tanto, necesita una manera de controlar la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="c8e65-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="c8e65-124">La versión 2.0 de .NET Framework presenta la `ICorDebugType` interfaz.</span><span class="sxs-lookup"><span data-stu-id="c8e65-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="c8e65-125">Para un tipo genérico, un `ICorDebugClass` o `ICorDebugClass2` objeto representa el tipo sin instancias (`SortedList<K,V>`) y un `ICorDebugType` representa los distintos tipos de instancias de objeto.</span><span class="sxs-lookup"><span data-stu-id="c8e65-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="c8e65-126">Dado un `ICorDebugClass` o `ICorDebugClass2` objeto, puede crear un `ICorDebugType` objeto para la creación de instancias mediante una llamada a la `ICorDebugClass2::GetParameterizedType` método.</span><span class="sxs-lookup"><span data-stu-id="c8e65-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="c8e65-127">También puede crear un `ICorDebugType` objeto para un tipo simple, como Int32, o para un tipo no genérico.</span><span class="sxs-lookup"><span data-stu-id="c8e65-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="c8e65-128">La introducción de la `ICorDebugType` que represente la noción de tiempo de ejecución de un tipo de objeto tiene un efecto dominó a lo largo de la API.</span><span class="sxs-lookup"><span data-stu-id="c8e65-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="c8e65-129">Funciones que realizó anteriormente una `ICorDebugClass` o `ICorDebugClass2` objeto o incluso un `CorElementType` valor están generalizados para tomar un `ICorDebugType` objeto.</span><span class="sxs-lookup"><span data-stu-id="c8e65-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8e65-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8e65-130">Requirements</span></span>  
 <span data-ttu-id="c8e65-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8e65-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8e65-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8e65-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8e65-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8e65-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8e65-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e65-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
