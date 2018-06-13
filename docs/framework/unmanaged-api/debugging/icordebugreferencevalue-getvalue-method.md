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
ms.openlocfilehash: 92df7bbcc2c391dd28f4075a97595762403d8def
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416320"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="be1e3-102">ICorDebugReferenceValue::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="be1e3-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="be1e3-103">Obtiene la dirección de memoria actual del objeto de referencia.</span><span class="sxs-lookup"><span data-stu-id="be1e3-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be1e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be1e3-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be1e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be1e3-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="be1e3-106">[out] Un puntero a un `CORDB_ADDRESS` valor que especifica la dirección del objeto al que apunta este objeto ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="be1e3-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be1e3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be1e3-107">Requirements</span></span>  
 <span data-ttu-id="be1e3-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be1e3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be1e3-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be1e3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be1e3-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be1e3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be1e3-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be1e3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
