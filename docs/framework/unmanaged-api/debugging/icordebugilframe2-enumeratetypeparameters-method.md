---
title: ICorDebugILFrame2::EnumerateTypeParameters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 73c17864047270302dbc115667eec4bf5ea1569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725054"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="c18eb-102">ICorDebugILFrame2::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="c18eb-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>

<span data-ttu-id="c18eb-103">Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="c18eb-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c18eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c18eb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c18eb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c18eb-105">Parameters</span></span>  

 `ppTyParEnum`  
 <span data-ttu-id="c18eb-106">Puntero a la dirección de un objeto de interfaz ICorDebugTypeEnum que permite la enumeración de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="c18eb-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="c18eb-107">La lista de parámetros de tipo incluye los parámetros de tipo de clase (si existen) seguidos de los parámetros de tipo de método (si existen).</span><span class="sxs-lookup"><span data-stu-id="c18eb-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c18eb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c18eb-108">Remarks</span></span>  

 <span data-ttu-id="c18eb-109">Use el método [IMetaDataImport2:: enumgenericparams (](../metadata/imetadataimport2-enumgenericparams-method.md) para determinar cuántos parámetros de tipo de clase y parámetros de tipo de método contiene esta lista.</span><span class="sxs-lookup"><span data-stu-id="c18eb-109">Use the [IMetaDataImport2::EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="c18eb-110">Los parámetros de tipo no están siempre disponibles.</span><span class="sxs-lookup"><span data-stu-id="c18eb-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c18eb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c18eb-111">Requirements</span></span>  

 <span data-ttu-id="c18eb-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c18eb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c18eb-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c18eb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c18eb-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c18eb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c18eb-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c18eb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
