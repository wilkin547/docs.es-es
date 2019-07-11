---
title: ICorDebugEval::CreateValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ada3a06a2beb8f21c3e24665c0f1f8e7c48515f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752950"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="f7407-102">ICorDebugEval::CreateValue (Método)</span><span class="sxs-lookup"><span data-stu-id="f7407-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="f7407-103">Crea un valor del tipo especificado, con un valor inicial de cero o null.</span><span class="sxs-lookup"><span data-stu-id="f7407-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="f7407-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="f7407-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f7407-105">Use [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f7407-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7407-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7407-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7407-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7407-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="f7407-108">[in] Un valor de la [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeración que especifica el tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="f7407-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="f7407-109">[in] Puntero a un [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) objeto que especifica la clase del valor, si el tipo no es un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="f7407-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f7407-110">[out] Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor.</span><span class="sxs-lookup"><span data-stu-id="f7407-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7407-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7407-111">Remarks</span></span>  
 <span data-ttu-id="f7407-112">`CreateValue` crea un `ICorDebugValue` objeto del tipo especificado con el único fin de utilizarlo en una evaluación de función.</span><span class="sxs-lookup"><span data-stu-id="f7407-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="f7407-113">Este objeto de valor puede utilizarse para pasar las constantes de usuario como parámetros.</span><span class="sxs-lookup"><span data-stu-id="f7407-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="f7407-114">Si el tipo del valor es un tipo primitivo, su valor inicial es cero o null.</span><span class="sxs-lookup"><span data-stu-id="f7407-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="f7407-115">Use [ICorDebugGenericValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) para establecer el valor de un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="f7407-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="f7407-116">Si el valor de `elementType` es ELEMENT_TYPE_CLASS, obtendrá un "ICorDebugReferenceValue" (devuelto en `ppValue`) que representa la referencia de objeto nulo.</span><span class="sxs-lookup"><span data-stu-id="f7407-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="f7407-117">Puede utilizar este objeto para pasar null para una evaluación de función que tiene parámetros de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="f7407-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="f7407-118">No puede establecer el `ICorDebugValue` a nada; siempre es null.</span><span class="sxs-lookup"><span data-stu-id="f7407-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7407-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7407-119">Requirements</span></span>  
 <span data-ttu-id="f7407-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7407-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7407-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7407-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7407-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7407-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7407-123">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="f7407-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7407-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7407-124">See also</span></span>

- [<span data-ttu-id="f7407-125">CreateValueForType (método)</span><span class="sxs-lookup"><span data-stu-id="f7407-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="f7407-126">ICorDebugEval (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7407-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
