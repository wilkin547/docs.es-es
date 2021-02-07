---
description: 'Más información acerca de: ICorDebugObjectValue:: GetFieldValue (método)'
title: ICorDebugObjectValue::GetFieldValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 38dac36747b286ab16ae3310b6b59695480a6ff1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722196"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="111e2-103">ICorDebugObjectValue::GetFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="111e2-103">ICorDebugObjectValue::GetFieldValue Method</span></span>

<span data-ttu-id="111e2-104">Obtiene el valor del campo especificado de la clase especificada para este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="111e2-104">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="111e2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="111e2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="111e2-106">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="111e2-107">de Un puntero a un objeto "ICorDebugClass" que representa la clase para la que se va a obtener el valor del campo.</span><span class="sxs-lookup"><span data-stu-id="111e2-107">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="111e2-108">de `mdFieldDef` Token que hace referencia a los metadatos que describen el campo.</span><span class="sxs-lookup"><span data-stu-id="111e2-108">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="111e2-109">enuncia Un puntero a un objeto "ICorDebugValue" que representa el valor del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="111e2-109">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="111e2-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="111e2-110">Remarks</span></span>  

 <span data-ttu-id="111e2-111">La clase, especificada en el `pClass` parámetro, debe estar en la jerarquía de la clase del valor del objeto y el campo debe ser un campo de esa clase.</span><span class="sxs-lookup"><span data-stu-id="111e2-111">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="111e2-112">El `GetFieldValue` método seguirá teniendo éxito para los objetos genéricos y las clases genéricas.</span><span class="sxs-lookup"><span data-stu-id="111e2-112">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="111e2-113">Por ejemplo, si \<V> se hereda de Dictionary \<string,V> y el valor del objeto es del tipo de diccionario \<int32> , el paso del `ICorDebugClass` objeto para el diccionario \<K,V> obtendrá correctamente un campo de diccionario \<string,int32> .</span><span class="sxs-lookup"><span data-stu-id="111e2-113">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="111e2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="111e2-114">Requirements</span></span>  

 <span data-ttu-id="111e2-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="111e2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111e2-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="111e2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="111e2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="111e2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="111e2-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111e2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111e2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="111e2-119">See also</span></span>
