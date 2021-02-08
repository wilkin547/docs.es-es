---
description: 'Más información sobre: ICorDebugILFrame2:: EnumerateTypeParameters ((método)'
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
ms.openlocfilehash: 34f305b7793e4909318ae2301d72e2af7c12f2c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791299"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="8327b-103">ICorDebugILFrame2::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="8327b-103">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>

<span data-ttu-id="8327b-104">Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="8327b-104">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8327b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8327b-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8327b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8327b-106">Parameters</span></span>  

 `ppTyParEnum`  
 <span data-ttu-id="8327b-107">Puntero a la dirección de un objeto de interfaz ICorDebugTypeEnum que permite la enumeración de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="8327b-107">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="8327b-108">La lista de parámetros de tipo incluye los parámetros de tipo de clase (si existen) seguidos de los parámetros de tipo de método (si existen).</span><span class="sxs-lookup"><span data-stu-id="8327b-108">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8327b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8327b-109">Remarks</span></span>  

 <span data-ttu-id="8327b-110">Use el método [IMetaDataImport2:: enumgenericparams (](../metadata/imetadataimport2-enumgenericparams-method.md) para determinar cuántos parámetros de tipo de clase y parámetros de tipo de método contiene esta lista.</span><span class="sxs-lookup"><span data-stu-id="8327b-110">Use the [IMetaDataImport2::EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="8327b-111">Los parámetros de tipo no están siempre disponibles.</span><span class="sxs-lookup"><span data-stu-id="8327b-111">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8327b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8327b-112">Requirements</span></span>  

 <span data-ttu-id="8327b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8327b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8327b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8327b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8327b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8327b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8327b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8327b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
