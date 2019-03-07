---
title: ICorDebugType::GetFirstTypeParameter (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d872e4a65c0556dddac468336e6a42dd7d7923c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477654"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="3c686-102">ICorDebugType::GetFirstTypeParameter (Método)</span><span class="sxs-lookup"><span data-stu-id="3c686-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="3c686-103">Obtiene un puntero de interfaz a una instancia de ICorDebugType que representa la primera <xref:System.Type> parámetro del tipo representado por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="3c686-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c686-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c686-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c686-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c686-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="3c686-106">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="3c686-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c686-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c686-107">Remarks</span></span>  
 <span data-ttu-id="3c686-108">`GetFirstTypeParameter` se puede llamar en casos donde la información adicional sobre el tipo implica, como máximo, un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="3c686-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="3c686-109">En concreto, se puede usar si el tipo es un ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR, tal y como indica la [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="3c686-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c686-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c686-110">Requirements</span></span>  
 <span data-ttu-id="3c686-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c686-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c686-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c686-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c686-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c686-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c686-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c686-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
