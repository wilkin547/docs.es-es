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
ms.openlocfilehash: cfc8800915009912716ec2ed9044a633a8ad0582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401750"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="8f8b9-102">ICorDebugBoxValue::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="8f8b9-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="8f8b9-103">Obtiene el valor de conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="8f8b9-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f8b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f8b9-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f8b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f8b9-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="8f8b9-106">[out] Un puntero a la dirección de un objeto ICorDebugObjectValue que representa el valor de conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="8f8b9-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f8b9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f8b9-107">Requirements</span></span>  
 <span data-ttu-id="8f8b9-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f8b9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f8b9-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f8b9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f8b9-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f8b9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f8b9-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f8b9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
