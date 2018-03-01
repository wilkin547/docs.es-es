---
title: "ICorDebugType::EnumerateTypeParameters (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d4b864b2b5fd4f2a6ed03218ce6e7b6f3bf62202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="cb3ab-102">ICorDebugType::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="cb3ab-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="cb3ab-103">Obtiene un puntero de interfaz a ICorDebugTypeEnum que contiene el <xref:System.Type> parámetros de la clase al que hace referencia esta instancia de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb3ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb3ab-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb3ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb3ab-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="cb3ab-106">[out] Un puntero a la dirección de un `ICorDebugTypeEnum` que contiene los parámetros del tipo.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb3ab-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb3ab-107">Remarks</span></span>  
 <span data-ttu-id="cb3ab-108">Puede usar `EnumerateTypeParameters` si el valor de CorElementType devuelto por [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) es ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR o ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="cb3ab-109">El número de parámetros y su orden depende del tipo:</span><span class="sxs-lookup"><span data-stu-id="cb3ab-109">The number of parameters and their order depends on the type:</span></span>  
  
-   <span data-ttu-id="cb3ab-110">ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: el número de parámetros de tipo contenido en el `ICorDebugTypeEnum` que devuelve este método, dependerá del número de parámetros de tipo formales para la clase correspondiente.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="cb3ab-111">Por ejemplo, si el tipo es `class Dict<String,int32>`, a continuación, `EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene objetos que representan `String` y `int32` en secuencia.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
-   <span data-ttu-id="cb3ab-112">ELEMENT_TYPE_FNPTR: El número de parámetros de tipo contenido en el `ICorDebugTypeEnum` será a uno mayor que el número de argumentos aceptados por la función.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="cb3ab-113">El primer parámetro de tipo contenido en el `ICorDebugTypeEnum` es el tipo de valor devuelto para la función y los parámetros de tipo posteriores son parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
-   <span data-ttu-id="cb3ab-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: se devolverá un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="cb3ab-115">Por ejemplo, si el tipo es un tipo de matriz como `int32[]`,`EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene un objeto que representa `int32`.</span><span class="sxs-lookup"><span data-stu-id="cb3ab-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb3ab-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb3ab-116">Requirements</span></span>  
 <span data-ttu-id="cb3ab-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb3ab-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb3ab-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb3ab-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb3ab-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb3ab-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb3ab-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb3ab-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
