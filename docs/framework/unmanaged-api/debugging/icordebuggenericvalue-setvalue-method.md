---
title: ICorDebugGenericValue::SetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
ms.openlocfilehash: 493793c45e7d13511e4c36fe76e472a856b50d72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705753"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="43b6f-102">ICorDebugGenericValue::SetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="43b6f-102">ICorDebugGenericValue::SetValue Method</span></span>

<span data-ttu-id="43b6f-103">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="43b6f-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43b6f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43b6f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43b6f-105">Parameters</span></span>  

 `pFrom`  
 <span data-ttu-id="43b6f-106">de Puntero al búfer desde el que se va a copiar el valor.</span><span class="sxs-lookup"><span data-stu-id="43b6f-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43b6f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43b6f-107">Remarks</span></span>  

 <span data-ttu-id="43b6f-108">En el caso de los tipos de referencia, el valor es la referencia, no el contenido.</span><span class="sxs-lookup"><span data-stu-id="43b6f-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b6f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43b6f-109">Requirements</span></span>  

 <span data-ttu-id="43b6f-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43b6f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b6f-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43b6f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43b6f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43b6f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43b6f-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43b6f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
