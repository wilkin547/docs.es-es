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
ms.openlocfilehash: 5e2fc054e42c34b13051e2125f8e18adc3029633
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755565"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="e5f4b-102">ICorDebugGenericValue::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="e5f4b-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="e5f4b-103">Copia el valor de este genérico en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="e5f4b-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5f4b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5f4b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5f4b-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="e5f4b-106">[out] Un puntero al valor representado por este objeto ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="e5f4b-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="e5f4b-107">El valor puede ser un tipo simple o un tipo de referencia (es decir, un puntero).</span><span class="sxs-lookup"><span data-stu-id="e5f4b-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f4b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5f4b-108">Requirements</span></span>  
 <span data-ttu-id="e5f4b-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5f4b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f4b-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5f4b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5f4b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5f4b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5f4b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f4b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
