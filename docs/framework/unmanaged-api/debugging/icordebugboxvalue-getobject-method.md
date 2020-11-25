---
title: ICorDebugBoxValue::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
ms.openlocfilehash: df151e9fc89214d0851ebe60c7ebdb87224f880c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719091"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="b0713-102">ICorDebugBoxValue::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="b0713-102">ICorDebugBoxValue::GetObject Method</span></span>

<span data-ttu-id="b0713-103">Obtiene el valor de la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="b0713-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0713-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0713-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0713-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0713-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="b0713-106">enuncia Puntero a la dirección de un objeto ICorDebugObjectValue que representa el valor de la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="b0713-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0713-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0713-107">Requirements</span></span>  

 <span data-ttu-id="b0713-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0713-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0713-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0713-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0713-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0713-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0713-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0713-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
