---
title: "ICorDebugCode::GetVersionNumber (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6efcfa60a6254081ea28aeb9d51f41410ab5049e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="81372-102">ICorDebugCode::GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="81372-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="81372-103">Obtiene el número basado en uno que identifica la versión del código que representa esta "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="81372-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81372-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81372-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81372-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81372-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="81372-106">[out] Un puntero al número de versión del código.</span><span class="sxs-lookup"><span data-stu-id="81372-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81372-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81372-107">Remarks</span></span>  
 <span data-ttu-id="81372-108">El número de versión se incrementa cada vez que se realiza una operación de (EnC) editar y continuar en el código.</span><span class="sxs-lookup"><span data-stu-id="81372-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81372-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81372-109">Requirements</span></span>  
 <span data-ttu-id="81372-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81372-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81372-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81372-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81372-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81372-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81372-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81372-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81372-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="81372-114">See Also</span></span>  
 
