---
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
ms.openlocfilehash: 745be25183f6b94e7a807c4230961d72e2836fe5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695340"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="0d819-102">ICorDebugObjectValue::GetFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="0d819-102">ICorDebugObjectValue::GetFieldValue Method</span></span>

<span data-ttu-id="0d819-103">Obtiene el valor del campo especificado de la clase especificada para este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="0d819-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d819-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d819-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d819-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d819-105">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="0d819-106">de Un puntero a un objeto "ICorDebugClass" que representa la clase para la que se va a obtener el valor del campo.</span><span class="sxs-lookup"><span data-stu-id="0d819-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="0d819-107">de `mdFieldDef` Token que hace referencia a los metadatos que describen el campo.</span><span class="sxs-lookup"><span data-stu-id="0d819-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0d819-108">enuncia Un puntero a un objeto "ICorDebugValue" que representa el valor del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="0d819-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d819-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d819-109">Remarks</span></span>  

 <span data-ttu-id="0d819-110">La clase, especificada en el `pClass` parámetro, debe estar en la jerarquía de la clase del valor del objeto y el campo debe ser un campo de esa clase.</span><span class="sxs-lookup"><span data-stu-id="0d819-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="0d819-111">El `GetFieldValue` método seguirá teniendo éxito para los objetos genéricos y las clases genéricas.</span><span class="sxs-lookup"><span data-stu-id="0d819-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="0d819-112">Por ejemplo, si \<V> se hereda de Dictionary \<string,V> y el valor del objeto es del tipo de diccionario \<int32> , el paso del `ICorDebugClass` objeto para el diccionario \<K,V> obtendrá correctamente un campo de diccionario \<string,int32> .</span><span class="sxs-lookup"><span data-stu-id="0d819-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d819-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d819-113">Requirements</span></span>  

 <span data-ttu-id="0d819-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d819-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d819-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d819-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d819-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d819-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d819-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d819-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d819-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d819-118">See also</span></span>
