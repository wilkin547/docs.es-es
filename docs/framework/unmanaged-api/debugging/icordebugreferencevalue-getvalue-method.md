---
title: ICorDebugReferenceValue::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5542cf5895bc60c5880f2f082a9c14d722e02478
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744924"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="8f9d1-102">ICorDebugReferenceValue::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="8f9d1-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="8f9d1-103">Obtiene la dirección de memoria actual del objeto que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="8f9d1-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f9d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f9d1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f9d1-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="8f9d1-106">[out] Un puntero a un `CORDB_ADDRESS` valor que especifica la dirección del objeto al que señala este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="8f9d1-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f9d1-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f9d1-107">Requirements</span></span>  
 <span data-ttu-id="8f9d1-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f9d1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f9d1-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f9d1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f9d1-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f9d1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f9d1-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f9d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
