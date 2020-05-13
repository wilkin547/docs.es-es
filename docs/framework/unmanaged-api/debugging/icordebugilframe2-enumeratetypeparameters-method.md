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
ms.openlocfilehash: 9020fed83b1c57cae3cc492872a279afb0195983
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205170"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="156c9-102">ICorDebugILFrame2::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="156c9-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="156c9-103">Obtiene un objeto ICorDebugTypeEnum que contiene los <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="156c9-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="156c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="156c9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="156c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="156c9-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="156c9-106">Puntero a la dirección de un objeto de interfaz ICorDebugTypeEnum que permite la enumeración de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="156c9-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="156c9-107">La lista de parámetros de tipo incluye los parámetros de tipo de clase (si existen) seguidos de los parámetros de tipo de método (si existen).</span><span class="sxs-lookup"><span data-stu-id="156c9-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="156c9-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="156c9-108">Remarks</span></span>  
 <span data-ttu-id="156c9-109">Use el método [IMetaDataImport2:: enumgenericparams (](../metadata/imetadataimport2-enumgenericparams-method.md) para determinar cuántos parámetros de tipo de clase y parámetros de tipo de método contiene esta lista.</span><span class="sxs-lookup"><span data-stu-id="156c9-109">Use the [IMetaDataImport2::EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="156c9-110">Los parámetros de tipo no están siempre disponibles.</span><span class="sxs-lookup"><span data-stu-id="156c9-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="156c9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="156c9-111">Requirements</span></span>  
 <span data-ttu-id="156c9-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="156c9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="156c9-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="156c9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="156c9-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="156c9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="156c9-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="156c9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
