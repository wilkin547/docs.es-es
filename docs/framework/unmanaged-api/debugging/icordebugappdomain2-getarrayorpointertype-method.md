---
title: ICorDebugAppDomain2::GetArrayOrPointerType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
ms.openlocfilehash: 8b3f6ae92e39f5385bf29f8b29abbb1726136088
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724772"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="c67d1-102">ICorDebugAppDomain2::GetArrayOrPointerType (Método)</span><span class="sxs-lookup"><span data-stu-id="c67d1-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>

<span data-ttu-id="c67d1-103">Obtiene una matriz del tipo especificado, o un puntero o una referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="c67d1-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c67d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c67d1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c67d1-105">Parameters</span></span>  

 `elementType`  
 <span data-ttu-id="c67d1-106">de Un valor de la enumeración CorElementType que especifica el tipo nativo subyacente (una matriz, puntero o referencia) que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c67d1-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="c67d1-107">de El rango (es decir, el número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c67d1-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="c67d1-108">Este valor debe ser 0 si `elementType` especifica un puntero o un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="c67d1-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="c67d1-109">de Un puntero a un objeto ICorDebugType que representa el tipo de matriz, puntero o referencia que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c67d1-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="c67d1-110">enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa la matriz construida, el tipo de puntero o el tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="c67d1-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c67d1-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c67d1-111">Remarks</span></span>  

 <span data-ttu-id="c67d1-112">El valor de *elementType* debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c67d1-112">The value of *elementType* must be one of the following:</span></span>  
  
- <span data-ttu-id="c67d1-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="c67d1-113">ELEMENT_TYPE_PTR</span></span>  
  
- <span data-ttu-id="c67d1-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="c67d1-114">ELEMENT_TYPE_BYREF</span></span>  
  
- <span data-ttu-id="c67d1-115">ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="c67d1-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="c67d1-116">Si el valor de *elementType* es ELEMENT_TYPE_PTR o ELEMENT_TYPE_BYREF, *nRank* debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="c67d1-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c67d1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c67d1-117">Requirements</span></span>  

 <span data-ttu-id="c67d1-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c67d1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c67d1-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c67d1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c67d1-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c67d1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c67d1-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c67d1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
