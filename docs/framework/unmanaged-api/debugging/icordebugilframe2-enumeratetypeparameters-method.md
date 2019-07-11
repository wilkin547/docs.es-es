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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2e53bfb46579cc51b7ad88ef7de2b9f8d2f9390
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758761"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="f037f-102">ICorDebugILFrame2::EnumerateTypeParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="f037f-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="f037f-103">Obtiene un objeto ICorDebugTypeEnum que contiene el <xref:System.Type> parámetros de este marco.</span><span class="sxs-lookup"><span data-stu-id="f037f-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f037f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f037f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f037f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f037f-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="f037f-106">Un puntero a la dirección de un objeto de interfaz ICorDebugTypeEnum que permite la enumeración de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="f037f-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="f037f-107">La lista de parámetros de tipo incluye los parámetros de tipo clase (si existe) seguidos de los parámetros de tipo de método (si existe).</span><span class="sxs-lookup"><span data-stu-id="f037f-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f037f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f037f-108">Remarks</span></span>  
 <span data-ttu-id="f037f-109">Use la [Imetadataimport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) método para determinar cuántos parámetros de tipo de clase y método esta lista contiene de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="f037f-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="f037f-110">Los parámetros de tipo no están siempre disponibles.</span><span class="sxs-lookup"><span data-stu-id="f037f-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f037f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f037f-111">Requirements</span></span>  
 <span data-ttu-id="f037f-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f037f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f037f-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f037f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f037f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f037f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f037f-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f037f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
