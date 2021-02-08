---
description: 'Más información acerca de: ICorDebugGenericValue:: SetValue (método)'
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
ms.openlocfilehash: e284d9987c8428fadedde0024fd3c65a0d8fe7a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791483"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="48d9f-103">ICorDebugGenericValue::SetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="48d9f-103">ICorDebugGenericValue::SetValue Method</span></span>

<span data-ttu-id="48d9f-104">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="48d9f-104">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d9f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48d9f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48d9f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48d9f-106">Parameters</span></span>  

 `pFrom`  
 <span data-ttu-id="48d9f-107">de Puntero al búfer desde el que se va a copiar el valor.</span><span class="sxs-lookup"><span data-stu-id="48d9f-107">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48d9f-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="48d9f-108">Remarks</span></span>  

 <span data-ttu-id="48d9f-109">En el caso de los tipos de referencia, el valor es la referencia, no el contenido.</span><span class="sxs-lookup"><span data-stu-id="48d9f-109">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d9f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48d9f-110">Requirements</span></span>  

 <span data-ttu-id="48d9f-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d9f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d9f-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48d9f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48d9f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48d9f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48d9f-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d9f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
