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
ms.openlocfilehash: be69636056d5510b72dbce39917f5e8d3b05cd87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723979"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="64309-102">ICorDebugType::GetFirstTypeParameter (Método)</span><span class="sxs-lookup"><span data-stu-id="64309-102">ICorDebugType::GetFirstTypeParameter Method</span></span>

<span data-ttu-id="64309-103">Obtiene un puntero de interfaz a una ICorDebugType que representa el primer <xref:System.Type> parámetro del tipo representado por este `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="64309-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64309-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64309-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64309-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64309-105">Parameters</span></span>  

 `value`  
 <span data-ttu-id="64309-106">enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="64309-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64309-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64309-107">Remarks</span></span>  

 <span data-ttu-id="64309-108">`GetFirstTypeParameter` se puede llamar a en casos en los que la información adicional sobre el tipo implique, como máximo, un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="64309-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="64309-109">En concreto, se puede utilizar si el tipo es un ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF o ELEMENT_TYPE_PTR, tal y como se indica en el método [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="64309-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64309-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64309-110">Requirements</span></span>  

 <span data-ttu-id="64309-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64309-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64309-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64309-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64309-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64309-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64309-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64309-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
