---
title: ICorDebugType (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 4f3f553ed5dc93433610365e0dae5bee54863de5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129624"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="b7d8e-102">ICorDebugType (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-102">ICorDebugType Interface</span></span>
<span data-ttu-id="b7d8e-103">Representa un tipo, ya sea básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="b7d8e-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="b7d8e-104">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7d8e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7d8e-105">Methods</span></span>  
  
|<span data-ttu-id="b7d8e-106">Método</span><span class="sxs-lookup"><span data-stu-id="b7d8e-106">Method</span></span>|<span data-ttu-id="b7d8e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7d8e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7d8e-108">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="b7d8e-109">Obtiene un puntero de interfaz a un ICorDebugTypeEnum que hace referencia a los parámetros de <xref:System.Type> genéricos de la clase a la que hace referencia este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="b7d8e-110">GetBase (método)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="b7d8e-111">Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia a la clase base de la clase a la que hace referencia este `ICorDebugType`, si existe uno.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="b7d8e-112">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="b7d8e-113">Obtiene un puntero de interfaz a un ICorDebugClass que hace referencia al constructor con tipo de este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="b7d8e-114">GetFirstTypeParameter (método)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="b7d8e-115">Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia al primer parámetro <xref:System.Type> genérico del constructor de la clase a la que hace referencia este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="b7d8e-116">GetRank (método)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="b7d8e-117">Obtiene el número de dimensiones de un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="b7d8e-118">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="b7d8e-119">Obtiene un puntero de interfaz a un ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="b7d8e-120">GetType (método)</span><span class="sxs-lookup"><span data-stu-id="b7d8e-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="b7d8e-121">Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime <xref:System.Type> al que hace referencia este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d8e-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7d8e-122">Remarks</span></span>  
 <span data-ttu-id="b7d8e-123">Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancia.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="b7d8e-124">La interfaz `ICorDebugType` representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="b7d8e-125">Por ejemplo, la tabla hash\<K, V > se representará mediante `ICorDebugClass`, mientras que la tabla Hashtable\<Int32, > de cadena se representará mediante `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="b7d8e-126">Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="b7d8e-127">La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7d8e-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b7d8e-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d8e-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7d8e-129">Requirements</span></span>  
 <span data-ttu-id="b7d8e-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d8e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d8e-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7d8e-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7d8e-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7d8e-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7d8e-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d8e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d8e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7d8e-134">See also</span></span>

- [<span data-ttu-id="b7d8e-135">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b7d8e-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
