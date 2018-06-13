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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 230666cefdadd56465fac35222500ad4b6da67e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418313"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="a5386-102">ICorDebugObjectValue::GetFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="a5386-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="a5386-103">Obtiene el valor del campo especificado de la clase especificada para este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="a5386-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5386-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5386-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5386-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5386-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="a5386-106">[in] Un puntero a un objeto de "ICorDebugClass" que representa la clase para la que se va a obtener el valor del campo.</span><span class="sxs-lookup"><span data-stu-id="a5386-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="a5386-107">[in] Un `mdFieldDef` símbolo (token) que hace referencia a los metadatos que describen el campo.</span><span class="sxs-lookup"><span data-stu-id="a5386-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a5386-108">[out] Un puntero a un objeto de "ICorDebugValue" que representa el valor del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="a5386-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5386-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5386-109">Remarks</span></span>  
 <span data-ttu-id="a5386-110">La clase, especificada en el `pClass` parámetro, debe estar en la jerarquía de clase del valor de objeto, y el campo debe ser un campo de esa clase.</span><span class="sxs-lookup"><span data-stu-id="a5386-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="a5386-111">El `GetFieldValue` método todavía tendrá éxito para objetos genéricos y clases genéricas.</span><span class="sxs-lookup"><span data-stu-id="a5386-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="a5386-112">Por ejemplo, si MyDictionary\<V > hereda de Dictionary\<string, V >, y el valor del objeto es de tipo MyDictionary\<int32 >, pasando el `ICorDebugClass` objeto de diccionario\<K, V > le Obtenga correctamente un campo del diccionario\<string, int32 >.</span><span class="sxs-lookup"><span data-stu-id="a5386-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5386-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5386-113">Requirements</span></span>  
 <span data-ttu-id="a5386-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5386-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5386-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5386-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5386-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5386-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5386-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5386-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5386-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5386-118">See Also</span></span>  
    
 
