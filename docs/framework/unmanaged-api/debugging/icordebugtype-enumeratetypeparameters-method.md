---
description: 'Más información sobre: ICorDebugType:: EnumerateTypeParameters ((método)'
title: ICorDebugType::EnumerateTypeParameters (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 5189394cbb39cd133ebce494107f4ca65660bb5b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658417"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="910e7-103">ICorDebugType::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="910e7-103">ICorDebugType::EnumerateTypeParameters Method</span></span>

<span data-ttu-id="910e7-104">Obtiene un puntero de interfaz a un ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de la clase a la que hace referencia esta ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="910e7-104">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="910e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="910e7-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="910e7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="910e7-106">Parameters</span></span>  

 `ppTyParEnum`  
 <span data-ttu-id="910e7-107">enuncia Puntero a la dirección de un `ICorDebugTypeEnum` que contiene los parámetros del tipo.</span><span class="sxs-lookup"><span data-stu-id="910e7-107">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="910e7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="910e7-108">Remarks</span></span>  

 <span data-ttu-id="910e7-109">Puede usar `EnumerateTypeParameters` si el valor de CorElementType devuelto por [ICorDebugType:: GetType](icordebugtype-gettype-method.md) es ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR o ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="910e7-109">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="910e7-110">El número de parámetros y su orden dependen del tipo:</span><span class="sxs-lookup"><span data-stu-id="910e7-110">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="910e7-111">ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: el número de parámetros de tipo contenidos en `ICorDebugTypeEnum` que devuelve este método dependerá del número de parámetros de tipo formal de la clase correspondiente.</span><span class="sxs-lookup"><span data-stu-id="910e7-111">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="910e7-112">Por ejemplo, si el tipo es `class Dict<String,int32>` , `EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` objeto que contiene objetos que representan `String` y `int32` en secuencia.</span><span class="sxs-lookup"><span data-stu-id="910e7-112">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="910e7-113">ELEMENT_TYPE_FNPTR: el número de parámetros de tipo contenidos en `ICorDebugTypeEnum` será uno mayor que el número de argumentos aceptado por la función.</span><span class="sxs-lookup"><span data-stu-id="910e7-113">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="910e7-114">El primer parámetro de tipo contenido en `ICorDebugTypeEnum` es el tipo de valor devuelto para la función y los parámetros de tipo subsiguientes son los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="910e7-114">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="910e7-115">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: se devolverá un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="910e7-115">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="910e7-116">Por ejemplo, si el tipo es un tipo de matriz como `int32[]` , `EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` objeto que contiene un objeto que representa `int32` .</span><span class="sxs-lookup"><span data-stu-id="910e7-116">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="910e7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="910e7-117">Requirements</span></span>  

 <span data-ttu-id="910e7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="910e7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="910e7-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="910e7-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="910e7-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="910e7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="910e7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="910e7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
