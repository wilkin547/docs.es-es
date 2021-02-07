---
description: 'Más información acerca de: ICorDebugEval:: CreateValue ((método)'
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
ms.openlocfilehash: f5ea753b5b95c68136e7b799aad88eee5845ea82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694167"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="3982d-103">ICorDebugEval::CreateValue (Método)</span><span class="sxs-lookup"><span data-stu-id="3982d-103">ICorDebugEval::CreateValue Method</span></span>

<span data-ttu-id="3982d-104">Crea un valor del tipo especificado, con un valor inicial de cero o null.</span><span class="sxs-lookup"><span data-stu-id="3982d-104">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="3982d-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="3982d-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3982d-106">Use [ICorDebugEval2:: createvaluefortype (](icordebugeval2-createvaluefortype-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3982d-106">Use [ICorDebugEval2::CreateValueForType](icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3982d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3982d-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3982d-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3982d-108">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="3982d-109">de Un valor de la enumeración [CorElementType](../metadata/corelementtype-enumeration.md) que especifica el tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="3982d-109">[in] A value of the [CorElementType](../metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="3982d-110">de Puntero a un objeto [ICorDebugClass](icordebugclass-interface.md) que especifica la clase del valor, si el tipo no es un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="3982d-110">[in] Pointer to an [ICorDebugClass](icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3982d-111">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor.</span><span class="sxs-lookup"><span data-stu-id="3982d-111">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3982d-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3982d-112">Remarks</span></span>  

 <span data-ttu-id="3982d-113">`CreateValue` crea un `ICorDebugValue` objeto del tipo especificado con el único fin de usarlo en una evaluación de función.</span><span class="sxs-lookup"><span data-stu-id="3982d-113">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="3982d-114">Este objeto de valor se puede usar para pasar constantes de usuario como parámetros.</span><span class="sxs-lookup"><span data-stu-id="3982d-114">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="3982d-115">Si el tipo del valor es un tipo primitivo, su valor inicial es cero o null.</span><span class="sxs-lookup"><span data-stu-id="3982d-115">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="3982d-116">Use [ICorDebugGenericValue:: SetValue](icordebuggenericvalue-setvalue-method.md) para establecer el valor de un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="3982d-116">Use [ICorDebugGenericValue::SetValue](icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="3982d-117">Si el valor de `elementType` es ELEMENT_TYPE_CLASS, obtendrá un "ICorDebugReferenceValue" (devuelto en `ppValue` ) que representa la referencia de objeto null.</span><span class="sxs-lookup"><span data-stu-id="3982d-117">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="3982d-118">Puede utilizar este objeto para pasar null a una evaluación de función que tenga parámetros de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="3982d-118">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="3982d-119">No se puede establecer `ICorDebugValue` en nada; siempre sigue siendo null.</span><span class="sxs-lookup"><span data-stu-id="3982d-119">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3982d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3982d-120">Requirements</span></span>  

 <span data-ttu-id="3982d-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3982d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3982d-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3982d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3982d-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3982d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3982d-124">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="3982d-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3982d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3982d-125">See also</span></span>

- [<span data-ttu-id="3982d-126">Método CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="3982d-126">CreateValueForType Method</span></span>](icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="3982d-127">Interfaz ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="3982d-127">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
