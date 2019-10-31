---
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
ms.openlocfilehash: 57a82e4ec106fead105cc7f200e7e56026004328
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122379"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="89582-102">ICorDebugType::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="89582-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="89582-103">Obtiene un puntero de interfaz a un ICorDebugTypeEnum que contiene los parámetros de <xref:System.Type> de la clase a la que hace referencia esta ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="89582-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89582-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89582-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89582-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89582-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="89582-106">enuncia Puntero a la dirección de una `ICorDebugTypeEnum` que contiene los parámetros del tipo.</span><span class="sxs-lookup"><span data-stu-id="89582-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89582-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89582-107">Remarks</span></span>  
 <span data-ttu-id="89582-108">Puede usar `EnumerateTypeParameters` si el valor de CorElementType devuelto por [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) es ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR o ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="89582-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="89582-109">El número de parámetros y su orden dependen del tipo:</span><span class="sxs-lookup"><span data-stu-id="89582-109">The number of parameters and their order depends on the type:</span></span>  
  
- <span data-ttu-id="89582-110">ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE: el número de parámetros de tipo contenidos en el `ICorDebugTypeEnum` que devuelve este método dependerá del número de parámetros de tipo formal de la clase correspondiente.</span><span class="sxs-lookup"><span data-stu-id="89582-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="89582-111">Por ejemplo, si el tipo es `class Dict<String,int32>`, `EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene objetos que representan `String` y `int32` en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="89582-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
- <span data-ttu-id="89582-112">ELEMENT_TYPE_FNPTR: el número de parámetros de tipo contenidos en el `ICorDebugTypeEnum` será uno mayor que el número de argumentos aceptados por la función.</span><span class="sxs-lookup"><span data-stu-id="89582-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="89582-113">El primer parámetro de tipo contenido en la `ICorDebugTypeEnum` es el tipo de valor devuelto para la función y los parámetros de tipo subsiguientes son los parámetros de la función.</span><span class="sxs-lookup"><span data-stu-id="89582-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
- <span data-ttu-id="89582-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR: se devolverá un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="89582-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="89582-115">Por ejemplo, si el tipo es un tipo de matriz, como `int32[]`,`EnumerateTypeParameters` devolverá un `ICorDebugTypeEnum` que contiene un objeto que representa `int32`.</span><span class="sxs-lookup"><span data-stu-id="89582-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89582-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89582-116">Requirements</span></span>  
 <span data-ttu-id="89582-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89582-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89582-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89582-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89582-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89582-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89582-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89582-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
