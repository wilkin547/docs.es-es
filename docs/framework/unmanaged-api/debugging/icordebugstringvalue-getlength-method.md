---
title: "ICorDebugStringValue::GetLength (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 129998bc2e7530aefefb2655a83cb04a9aa4cc6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="d488f-102">ICorDebugStringValue::GetLength (Método)</span><span class="sxs-lookup"><span data-stu-id="d488f-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="d488f-103">Obtiene el número de caracteres de la cadena al que hace referencia este ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="d488f-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d488f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d488f-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d488f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d488f-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="d488f-106">[out] Un puntero a un valor que especifica la longitud de la cadena que hace referencia esta `ICorDebugStringValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="d488f-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d488f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d488f-107">Requirements</span></span>  
 <span data-ttu-id="d488f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d488f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d488f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d488f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d488f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d488f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d488f-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d488f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
