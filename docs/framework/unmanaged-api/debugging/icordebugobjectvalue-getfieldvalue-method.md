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
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095879"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="c176a-102">ICorDebugObjectValue::GetFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="c176a-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="c176a-103">Obtiene el valor del campo especificado de la clase especificada para este valor de objeto.</span><span class="sxs-lookup"><span data-stu-id="c176a-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c176a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c176a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c176a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c176a-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="c176a-106">de Un puntero a un objeto "ICorDebugClass" que representa la clase para la que se va a obtener el valor del campo.</span><span class="sxs-lookup"><span data-stu-id="c176a-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="c176a-107">de `mdFieldDef` token que hace referencia a los metadatos que describen el campo.</span><span class="sxs-lookup"><span data-stu-id="c176a-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c176a-108">enuncia Un puntero a un objeto "ICorDebugValue" que representa el valor del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="c176a-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c176a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c176a-109">Remarks</span></span>  
 <span data-ttu-id="c176a-110">La clase, especificada en el parámetro `pClass`, debe estar en la jerarquía de la clase del valor del objeto y el campo debe ser un campo de esa clase.</span><span class="sxs-lookup"><span data-stu-id="c176a-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="c176a-111">El método `GetFieldValue` seguirá teniendo éxito para los objetos genéricos y las clases genéricas.</span><span class="sxs-lookup"><span data-stu-id="c176a-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="c176a-112">Por ejemplo, si el Diccionario\<V > hereda del diccionario\<cadena, V >, y el valor del objeto es de tipo Dictionary\<Int32 >, pasando el objeto `ICorDebugClass` para el Diccionario\<K, V > obtendrá correctamente un campo de Dictionary\<String, Int32 >.</span><span class="sxs-lookup"><span data-stu-id="c176a-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c176a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c176a-113">Requirements</span></span>  
 <span data-ttu-id="c176a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c176a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c176a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c176a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c176a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c176a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c176a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c176a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c176a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c176a-118">See also</span></span>
