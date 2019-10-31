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
ms.openlocfilehash: 715ff5d4a06b53361d550f04e5154023d0b641bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095122"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="be724-102">ICorDebugILFrame2::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="be724-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="be724-103">Obtiene un objeto ICorDebugTypeEnum que contiene los parámetros de <xref:System.Type> de este marco.</span><span class="sxs-lookup"><span data-stu-id="be724-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be724-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be724-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be724-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be724-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="be724-106">Puntero a la dirección de un objeto de interfaz ICorDebugTypeEnum que permite la enumeración de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="be724-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="be724-107">La lista de parámetros de tipo incluye los parámetros de tipo de clase (si existen) seguidos de los parámetros de tipo de método (si existen).</span><span class="sxs-lookup"><span data-stu-id="be724-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be724-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be724-108">Remarks</span></span>  
 <span data-ttu-id="be724-109">Use el método [IMetaDataImport2:: enumgenericparams (](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) para determinar cuántos parámetros de tipo de clase y parámetros de tipo de método contiene esta lista.</span><span class="sxs-lookup"><span data-stu-id="be724-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="be724-110">Los parámetros de tipo no están siempre disponibles.</span><span class="sxs-lookup"><span data-stu-id="be724-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be724-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be724-111">Requirements</span></span>  
 <span data-ttu-id="be724-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be724-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be724-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be724-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be724-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be724-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be724-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be724-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
