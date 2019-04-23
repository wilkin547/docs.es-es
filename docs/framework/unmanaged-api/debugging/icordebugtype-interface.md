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
ms.openlocfilehash: 74863af1096f8600b8095e593c1f3c820c512e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166808"
---
# <a name="icordebugtype-interface"></a><span data-ttu-id="c0ac9-102">Interfaz ICorDebugType</span><span class="sxs-lookup"><span data-stu-id="c0ac9-102">ICorDebugType Interface</span></span>
<span data-ttu-id="c0ac9-103">Representa un tipo, básico o complejo (que es, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="c0ac9-103">Represents a type, either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="c0ac9-104">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-104">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0ac9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c0ac9-105">Methods</span></span>  
  
|<span data-ttu-id="c0ac9-106">Método</span><span class="sxs-lookup"><span data-stu-id="c0ac9-106">Method</span></span>|<span data-ttu-id="c0ac9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0ac9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0ac9-108">EnumerateTypeParameters (método)</span><span class="sxs-lookup"><span data-stu-id="c0ac9-108">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|<span data-ttu-id="c0ac9-109">Obtiene un puntero de interfaz a ICorDebugTypeEnum que hace referencia el tipo genérico <xref:System.Type> parámetros de la clase que hace referencia esta `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-109">Gets an interface pointer to an ICorDebugTypeEnum that references the generic <xref:System.Type> parameters of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="c0ac9-110">GetBase (método)</span><span class="sxs-lookup"><span data-stu-id="c0ac9-110">GetBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|<span data-ttu-id="c0ac9-111">Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia a la clase base de la clase que hace referencia esta `ICorDebugType`, si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-111">Gets an interface pointer to an `ICorDebugType` that references the base class of the class referenced by this `ICorDebugType`, if one exists.</span></span>|  
|[<span data-ttu-id="c0ac9-112">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="c0ac9-112">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|<span data-ttu-id="c0ac9-113">Obtiene un puntero de interfaz a ICorDebugClass que hace referencia al constructor con tipo de este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-113">Gets an interface pointer to an ICorDebugClass that references the typed constructor of this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="c0ac9-114">GetFirstTypeParameter (método)</span><span class="sxs-lookup"><span data-stu-id="c0ac9-114">GetFirstTypeParameter Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|<span data-ttu-id="c0ac9-115">Obtiene un puntero de interfaz a un `ICorDebugType` que hace referencia a la primera genérica <xref:System.Type> parámetro para el constructor de la clase que hace referencia esta `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-115">Gets an interface pointer to an `ICorDebugType` that references the first generic <xref:System.Type> parameter for the constructor of the class referenced by this `ICorDebugType`.</span></span>|  
|[<span data-ttu-id="c0ac9-116">GetRank (método)</span><span class="sxs-lookup"><span data-stu-id="c0ac9-116">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|<span data-ttu-id="c0ac9-117">Obtiene el número de dimensiones en un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-117">Gets the number of dimensions in an array type.</span></span>|  
|[<span data-ttu-id="c0ac9-118">GetStaticFieldValue (método)</span><span class="sxs-lookup"><span data-stu-id="c0ac9-118">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|<span data-ttu-id="c0ac9-119">Obtiene un puntero de interfaz al ICorDebugValue que contiene el valor del campo estático al que hace referencia el campo especificado token en el marco de pila especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-119">Gets an interface pointer to an ICorDebugValue that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>|  
|[<span data-ttu-id="c0ac9-120">GetType (método)</span><span class="sxs-lookup"><span data-stu-id="c0ac9-120">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|<span data-ttu-id="c0ac9-121">Obtiene un valor de CorElementType que describe el tipo nativo de common language runtime <xref:System.Type> hace referencia este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-121">Gets a CorElementType value that describes the native type of the common language runtime <xref:System.Type> referenced by this `ICorDebugType`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0ac9-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0ac9-122">Remarks</span></span>  
 <span data-ttu-id="c0ac9-123">Si el tipo es genérico, `ICorDebugClass` representa el tipo sin instancias.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-123">If the type is generic, `ICorDebugClass` represents the uninstantiated type.</span></span> <span data-ttu-id="c0ac9-124">El `ICorDebugType` interfaz representa un tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-124">The `ICorDebugType` interface represents an instantiated generic type.</span></span> <span data-ttu-id="c0ac9-125">Por ejemplo, Hashtable\<K, V > se representaría mediante `ICorDebugClass`, mientras que Hashtable\<Int32, String > se representaría mediante `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-125">For example, Hashtable\<K, V> would be represented by `ICorDebugClass`, whereas Hashtable\<Int32, String> would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="c0ac9-126">Los tipos no genéricos se representan mediante dos `ICorDebugClass` y `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-126">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="c0ac9-127">La última interfaz se introdujo en la versión 2.0 de .NET Framework para tratar con la creación de instancias de tipo.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-127">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0ac9-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c0ac9-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ac9-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0ac9-129">Requirements</span></span>  
 <span data-ttu-id="c0ac9-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ac9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ac9-131">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0ac9-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0ac9-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ac9-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0ac9-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ac9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ac9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0ac9-134">See also</span></span>

- [<span data-ttu-id="c0ac9-135">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c0ac9-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
