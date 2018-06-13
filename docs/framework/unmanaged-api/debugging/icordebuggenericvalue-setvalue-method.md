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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83aebad108a743d25b8ea93c99060d10bf5c3980
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413213"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="5ec15-102">ICorDebugGenericValue::SetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="5ec15-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="5ec15-103">Copia un nuevo valor del búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="5ec15-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec15-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ec15-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ec15-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ec15-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="5ec15-106">[in] Un puntero al búfer desde el que se va a copiar el valor.</span><span class="sxs-lookup"><span data-stu-id="5ec15-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ec15-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ec15-107">Remarks</span></span>  
 <span data-ttu-id="5ec15-108">Para los tipos de referencia, el valor es la referencia, no el contenido.</span><span class="sxs-lookup"><span data-stu-id="5ec15-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ec15-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ec15-109">Requirements</span></span>  
 <span data-ttu-id="5ec15-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ec15-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ec15-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ec15-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ec15-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ec15-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ec15-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ec15-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
