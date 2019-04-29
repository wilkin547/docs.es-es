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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c20eec52b0e4616af1b864bb58b6cbff44a720eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645401"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="1e362-102">ICorDebugBoxValue::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="1e362-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="1e362-103">Obtiene el valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="1e362-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e362-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e362-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e362-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e362-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="1e362-106">[out] Un puntero a la dirección de un objeto ICorDebugObjectValue que representa el valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="1e362-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e362-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e362-107">Requirements</span></span>  
 <span data-ttu-id="1e362-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e362-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e362-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e362-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e362-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e362-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e362-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e362-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
