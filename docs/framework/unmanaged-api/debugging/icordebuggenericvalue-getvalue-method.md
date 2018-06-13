---
title: ICorDebugGenericValue::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6d30a9f03d8717486be7cd89bb182d350a82df7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411641"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="801e3-102">ICorDebugGenericValue::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="801e3-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="801e3-103">Copia el valor de este genérico en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="801e3-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="801e3-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="801e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="801e3-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="801e3-106">[out] Un puntero al valor representado por este objeto ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="801e3-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="801e3-107">El valor puede ser un tipo simple o un tipo de referencia (es decir, un puntero).</span><span class="sxs-lookup"><span data-stu-id="801e3-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="801e3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="801e3-108">Requirements</span></span>  
 <span data-ttu-id="801e3-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="801e3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="801e3-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="801e3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="801e3-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="801e3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="801e3-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="801e3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
