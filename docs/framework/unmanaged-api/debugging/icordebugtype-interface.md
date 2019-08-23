---
title: Interfaz ICorDebugType
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964753"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="f12f8-102">Interfaz ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="f12f8-102">ICorDebugType Interface</span></span>
<span data-ttu-id="f12f8-103">Representa un tipo, ya sea básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="f12f8-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="f12f8-104">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="f12f8-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f12f8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f12f8-105">Methods</span></span>  
  
|<span data-ttu-id="f12f8-106">Método</span><span class="sxs-lookup"><span data-stu-id="f12f8-106">Method</span></span>|<span data-ttu-id="f12f8-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f12f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f12f8-108">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="f12f8-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="f12f8-109">Obtiene un puntero de interfaz a un ICorDebugTypeEnum que hace referencia <xref:System.Type> a los parámetros genéricos de la clase `ICorDebugType`a la que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f12f8-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="f12f8-110">GetBase (método)</span><span class="sxs-lookup"><span data-stu-id="f12f8-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="f12f8-111">Obtiene un puntero de interfaz a `ICorDebugType` que hace referencia a la clase base de la clase a la `ICorDebugType`que hace referencia, si existe una.</span><span class="sxs-lookup"><span data-stu-id="f12f8-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="f12f8-112">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="f12f8-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="f12f8-113">Obtiene un puntero de interfaz a un ICorDebugClass que hace referencia al constructor con tipo `ICorDebugType`de este.</span><span class="sxs-lookup"><span data-stu-id="f12f8-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="f12f8-114">GetFirstTypeParameter (método)</span><span class="sxs-lookup"><span data-stu-id="f12f8-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="f12f8-115">Obtiene un puntero de interfaz a `ICorDebugType` un que hace referencia al <xref:System.Type> primer parámetro genérico del constructor de la `ICorDebugType`clase a la que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f12f8-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="f12f8-116">GetRank (método)</span><span class="sxs-lookup"><span data-stu-id="f12f8-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="f12f8-117">Obtiene el número de dimensiones de un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="f12f8-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="f12f8-118">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="f12f8-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="f12f8-119">Obtiene un puntero de interfaz a un ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.</span><span class="sxs-lookup"><span data-stu-id="f12f8-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="f12f8-120">GetType (método)</span><span class="sxs-lookup"><span data-stu-id="f12f8-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="f12f8-121">Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime <xref:System.Type> al que hace referencia `ICorDebugType`este.</span><span class="sxs-lookup"><span data-stu-id="f12f8-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f12f8-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f12f8-122">Remarks</span></span>  
 <span data-ttu-id="f12f8-123">Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancia.</span><span class="sxs-lookup"><span data-stu-id="f12f8-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="f12f8-124">La `ICorDebugType` interfaz representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="f12f8-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="f12f8-125">Por ejemplo, la\<tabla hash K, V > sería representada por\< `ICorDebugClass`, mientras que la tabla hash Int32, `ICorDebugType`String > se representaría mediante.</span><span class="sxs-lookup"><span data-stu-id="f12f8-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="f12f8-126">Los `ICorDebugClass` tipos no genéricos están representados `ICorDebugType`por y.</span><span class="sxs-lookup"><span data-stu-id="f12f8-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="f12f8-127">La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="f12f8-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f12f8-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f12f8-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f12f8-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f12f8-129">Requirements</span></span>  
 <span data-ttu-id="f12f8-130">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f12f8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f12f8-131">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f12f8-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f12f8-132">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f12f8-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f12f8-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f12f8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f12f8-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f12f8-134">See also</span></span>

- [<span data-ttu-id="f12f8-135">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f12f8-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
