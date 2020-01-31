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
ms.openlocfilehash: 8210e67f4bdd615ff65d9bd3474043fc45fd8883
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791259"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="43c31-102">Interfaz ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="43c31-102">ICorDebugType Interface</span></span>
<span data-ttu-id="43c31-103">Representa un tipo, ya sea básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="43c31-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="43c31-104">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="43c31-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43c31-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="43c31-105">Methods</span></span>  
  
|<span data-ttu-id="43c31-106">Método</span><span class="sxs-lookup"><span data-stu-id="43c31-106">Method</span></span>|<span data-ttu-id="43c31-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="43c31-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43c31-108">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="43c31-108">EnumerateTypeParameters Method</span></span>](icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="43c31-109">Obtiene un puntero de interfaz a un ICorDebugTypeEnum que hace referencia a los parámetros de <xref:System.Type> genéricos de la clase a la que hace referencia este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="43c31-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="43c31-110">GetBase (método)</span><span class="sxs-lookup"><span data-stu-id="43c31-110">GetBase Method</span></span>](icordebugtype-getbase-method.md)|<span data-ttu-id="43c31-111">Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia a la clase base de la clase a la que hace referencia este `ICorDebugType`, si existe uno.</span><span class="sxs-lookup"><span data-stu-id="43c31-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="43c31-112">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="43c31-112">GetClass Method</span></span>](icordebugtype-getclass-method.md)|<span data-ttu-id="43c31-113">Obtiene un puntero de interfaz a un ICorDebugClass que hace referencia al constructor con tipo de este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="43c31-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="43c31-114">GetFirstTypeParameter (método)</span><span class="sxs-lookup"><span data-stu-id="43c31-114">GetFirstTypeParameter Method</span></span>](icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="43c31-115">Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia al primer parámetro <xref:System.Type> genérico del constructor de la clase a la que hace referencia este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="43c31-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="43c31-116">GetRank (método)</span><span class="sxs-lookup"><span data-stu-id="43c31-116">GetRank Method</span></span>](icordebugtype-getrank-method.md)|<span data-ttu-id="43c31-117">Obtiene el número de dimensiones de un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="43c31-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="43c31-118">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="43c31-118">GetStaticFieldValue Method</span></span>](icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="43c31-119">Obtiene un puntero de interfaz a un ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.</span><span class="sxs-lookup"><span data-stu-id="43c31-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="43c31-120">GetType (método)</span><span class="sxs-lookup"><span data-stu-id="43c31-120">GetType Method</span></span>](icordebugtype-gettype-method.md)|<span data-ttu-id="43c31-121">Obtiene un valor de CorElementType que describe el tipo nativo del Common Language Runtime <xref:System.Type> al que hace referencia este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="43c31-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43c31-122">Notas</span><span class="sxs-lookup"><span data-stu-id="43c31-122">Remarks</span></span>  
 <span data-ttu-id="43c31-123">Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancia.</span><span class="sxs-lookup"><span data-stu-id="43c31-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="43c31-124">La interfaz `ICorDebugType` representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="43c31-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="43c31-125">Por ejemplo, la tabla hash\<K, V > se representará mediante `ICorDebugClass`, mientras que la tabla Hashtable\<Int32, > de cadena se representará mediante `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="43c31-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="43c31-126">Los tipos no genéricos están representados por `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="43c31-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="43c31-127">La última interfaz se presentó en la .NET Framework versión 2,0 para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="43c31-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43c31-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="43c31-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c31-129">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="43c31-129">Requirements</span></span>  
 <span data-ttu-id="43c31-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c31-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c31-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43c31-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43c31-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43c31-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43c31-133">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c31-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c31-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="43c31-134">See also</span></span>

- [<span data-ttu-id="43c31-135">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="43c31-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
