---
title: "ICorDebugCode::IsIL (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.IsIL
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3530b5a7a747816a12e76d00fa7c299acf7657c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="0564b-102">ICorDebugCode::IsIL (Método)</span><span class="sxs-lookup"><span data-stu-id="0564b-102">ICorDebugCode::IsIL Method</span></span>
<span data-ttu-id="0564b-103">Obtiene un valor que indica si este "ICorDebugCode" representa el código que se compiló en lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="0564b-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0564b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0564b-104">Syntax</span></span>  
  
```  
HRESULT IsIL (  
    [out] BOOL       *pbIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0564b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0564b-105">Parameters</span></span>  
 `pbIL`  
 <span data-ttu-id="0564b-106">[out] `true` si `ICorDebugCode` representa el código que se ha compilado en MSIL; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0564b-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0564b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0564b-107">Requirements</span></span>  
 <span data-ttu-id="0564b-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0564b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0564b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0564b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0564b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0564b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0564b-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0564b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0564b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0564b-112">See Also</span></span>  
 
