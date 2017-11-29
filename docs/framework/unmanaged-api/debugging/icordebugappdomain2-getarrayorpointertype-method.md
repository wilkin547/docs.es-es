---
title: "ICorDebugAppDomain2::GetArrayOrPointerType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2.GetArrayOrPointerType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c08a56ff7f6bd109c5568a7f992850708a22a4b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="04de5-102">ICorDebugAppDomain2::GetArrayOrPointerType (Método)</span><span class="sxs-lookup"><span data-stu-id="04de5-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="04de5-103">Obtiene una matriz del tipo especificado, o un puntero o referencia al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="04de5-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04de5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04de5-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04de5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04de5-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="04de5-106">[in] Un valor de la enumeración CorElementType que especifica el tipo nativo subyacente (una matriz, puntero o referencia), que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="04de5-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="04de5-107">[in] El rango (es decir, el número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="04de5-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="04de5-108">Este valor debe ser 0 si `elementType` especifica un tipo de puntero o referencia.</span><span class="sxs-lookup"><span data-stu-id="04de5-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="04de5-109">[in] Un puntero a un objeto ICorDebugType que representa el tipo de matriz, puntero o referencia al crearse.</span><span class="sxs-lookup"><span data-stu-id="04de5-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="04de5-110">[out] Un puntero a la dirección de un `ICorDebugType` tipo de objeto que representa la matriz construida, tipo de puntero o referencia.</span><span class="sxs-lookup"><span data-stu-id="04de5-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04de5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04de5-111">Remarks</span></span>  
 <span data-ttu-id="04de5-112">El valor de *elementType* debe ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="04de5-112">The value of *elementType* must be one of the following:</span></span>  
  
-   <span data-ttu-id="04de5-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="04de5-113">ELEMENT_TYPE_PTR</span></span>  
  
-   <span data-ttu-id="04de5-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="04de5-114">ELEMENT_TYPE_BYREF</span></span>  
  
-   <span data-ttu-id="04de5-115">ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="04de5-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="04de5-116">Si el valor de *elementType* es ELEMENT_TYPE_PTR o ELEMENT_TYPE_BYREF, *nRank* debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="04de5-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04de5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04de5-117">Requirements</span></span>  
 <span data-ttu-id="04de5-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04de5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04de5-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04de5-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04de5-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04de5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04de5-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04de5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
