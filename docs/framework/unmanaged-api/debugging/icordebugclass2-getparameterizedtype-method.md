---
title: ICorDebugClass2::GetParameterizedType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 64537ab97c1256cc6f963999b027bafc25cbbccb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125730"
---
# <a name="icordebugclass2getparameterizedtype-method"></a><span data-ttu-id="56254-102">ICorDebugClass2::GetParameterizedType (Método)</span><span class="sxs-lookup"><span data-stu-id="56254-102">ICorDebugClass2::GetParameterizedType Method</span></span>
<span data-ttu-id="56254-103">Obtiene la declaración de tipos para esta clase.</span><span class="sxs-lookup"><span data-stu-id="56254-103">Gets the type declaration for this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56254-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56254-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56254-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56254-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="56254-106">de Un valor de la enumeración CorElementType que especifica el tipo de elemento para esta clase: establezca este valor en ELEMENT_TYPE_VALUETYPE si este ICorDebugClass2 representa un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="56254-106">[in] A value of the CorElementType enumeration that specifies the element type for this class: Set this value to ELEMENT_TYPE_VALUETYPE if this ICorDebugClass2 represents a value type.</span></span> <span data-ttu-id="56254-107">Establezca este valor en ELEMENT_TYPE_CLASS si este `ICorDebugClass2` representa un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="56254-107">Set this value to ELEMENT_TYPE_CLASS if this `ICorDebugClass2` represents a complex type.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="56254-108">de El número de parámetros de tipo, si el tipo es genérico.</span><span class="sxs-lookup"><span data-stu-id="56254-108">[in] The number of type parameters, if the type is generic.</span></span> <span data-ttu-id="56254-109">El número de parámetros de tipo (si existen) debe coincidir con el número requerido por la clase.</span><span class="sxs-lookup"><span data-stu-id="56254-109">The number of type parameters (if any) must match the number required by the class.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="56254-110">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="56254-110">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type parameter.</span></span> <span data-ttu-id="56254-111">Si la clase no es genérica, este valor es NULL.</span><span class="sxs-lookup"><span data-stu-id="56254-111">If the class is non-generic, this value is null.</span></span>  
  
 `ppType`  
 <span data-ttu-id="56254-112">enuncia Puntero a la dirección de un objeto `ICorDebugType` que representa la declaración de tipos.</span><span class="sxs-lookup"><span data-stu-id="56254-112">[out] A pointer to the address of an `ICorDebugType` object that represents the type declaration.</span></span> <span data-ttu-id="56254-113">Este objeto es equivalente a un objeto <xref:System.Type> en código administrado.</span><span class="sxs-lookup"><span data-stu-id="56254-113">This object is equivalent to a <xref:System.Type> object in managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56254-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56254-114">Remarks</span></span>  
 <span data-ttu-id="56254-115">Si la clase no es genérica, es decir, si no tiene parámetros de tipo, `GetParameterizedType` simplemente obtiene el objeto de tipo en tiempo de ejecución correspondiente a la clase.</span><span class="sxs-lookup"><span data-stu-id="56254-115">If the class is non-generic, that is, if it has no type parameters, `GetParameterizedType` simply gets the runtime type object corresponding to the class.</span></span> <span data-ttu-id="56254-116">El parámetro `elementType` debe establecerse en el tipo de elemento correcto para la clase: ELEMENT_TYPE_VALUETYPE si la clase es un tipo de valor; de lo contrario, ELEMENT_TYPE_CLASS.</span><span class="sxs-lookup"><span data-stu-id="56254-116">The `elementType` parameter should be set to the correct element type for the class: ELEMENT_TYPE_VALUETYPE if the class is a value type; otherwise, ELEMENT_TYPE_CLASS.</span></span>  
  
 <span data-ttu-id="56254-117">Si la clase acepta parámetros de tipo (por ejemplo, `ArrayList<T>`), puede usar `GetParameterizedType` para construir un objeto de tipo para un tipo con instancias como `ArrayList<int>`.</span><span class="sxs-lookup"><span data-stu-id="56254-117">If the class accepts type parameters (for example, `ArrayList<T>`), you can use `GetParameterizedType` to construct a type object for an instantiated type such as `ArrayList<int>`.</span></span>  
  
## <a name="background-information"></a><span data-ttu-id="56254-118">Información general</span><span class="sxs-lookup"><span data-stu-id="56254-118">Background Information</span></span>  
 <span data-ttu-id="56254-119">En las versiones .NET Framework 1,0 y 1,1, cada tipo de los metadatos se puede asignar directamente a un tipo en el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="56254-119">In the .NET Framework versions 1.0 and 1.1, every type in the metadata could be directly mapped to a type in the running process.</span></span> <span data-ttu-id="56254-120">Por lo tanto, un tipo de metadatos y un tipo en tiempo de ejecución tenían una única representación en el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="56254-120">Thus, a metadata type and a runtime type had a single representation in the running process.</span></span> <span data-ttu-id="56254-121">Sin embargo, un tipo genérico en los metadatos se puede asignar a muchas instancias diferentes del tipo en el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="56254-121">However, one generic type in metadata can be mapped to many different instantiations of the type in the running process.</span></span> <span data-ttu-id="56254-122">Por ejemplo, el tipo de metadatos `SortedList<K,V>` puede asignar a `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, etc.</span><span class="sxs-lookup"><span data-stu-id="56254-122">For example, the metadata type `SortedList<K,V>` can map to `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`, and so on.</span></span> <span data-ttu-id="56254-123">Por lo tanto, necesita una manera de controlar la creación de instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="56254-123">Thus, you need a way to handle type instantiation.</span></span>  
  
 <span data-ttu-id="56254-124">La versión 2,0 de .NET Framework presenta la interfaz `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="56254-124">The .NET Framework version 2.0 introduces the `ICorDebugType` interface.</span></span> <span data-ttu-id="56254-125">Para un tipo genérico, un objeto `ICorDebugClass` o `ICorDebugClass2` representa el tipo sin instancia (`SortedList<K,V>`) y un objeto `ICorDebugType` representa los distintos tipos con instancias.</span><span class="sxs-lookup"><span data-stu-id="56254-125">For a generic type, an `ICorDebugClass` or `ICorDebugClass2` object represents the uninstantiated type (`SortedList<K,V>`), and an `ICorDebugType` object represents the various instantiated types.</span></span> <span data-ttu-id="56254-126">Dado un objeto `ICorDebugClass` o `ICorDebugClass2`, puede crear un objeto `ICorDebugType` para cualquier instancia de mediante una llamada al método `ICorDebugClass2::GetParameterizedType`.</span><span class="sxs-lookup"><span data-stu-id="56254-126">Given an `ICorDebugClass` or `ICorDebugClass2` object, you can create an `ICorDebugType` object for any instantiation by calling the `ICorDebugClass2::GetParameterizedType` method.</span></span> <span data-ttu-id="56254-127">También puede crear un objeto `ICorDebugType` para un tipo simple, como Int32, o para un tipo no genérico.</span><span class="sxs-lookup"><span data-stu-id="56254-127">You can also create an `ICorDebugType` object for a simple type, such as Int32, or for a non-generic type.</span></span>  
  
 <span data-ttu-id="56254-128">La introducción del objeto `ICorDebugType` para representar la noción en tiempo de ejecución de un tipo tiene un efecto de rizo en toda la API.</span><span class="sxs-lookup"><span data-stu-id="56254-128">The introduction of the `ICorDebugType` object to represent the run-time notion of a type has a ripple effect throughout the API.</span></span> <span data-ttu-id="56254-129">Las funciones que anteriormente tomaban un objeto `ICorDebugClass` o `ICorDebugClass2` o incluso un valor de `CorElementType` se generalizan para tomar un objeto `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="56254-129">Functions that previously took an `ICorDebugClass` or `ICorDebugClass2` object or even a `CorElementType` value are generalized to take an `ICorDebugType` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56254-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56254-130">Requirements</span></span>  
 <span data-ttu-id="56254-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56254-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56254-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56254-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56254-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56254-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56254-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56254-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
