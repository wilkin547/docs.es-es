---
title: ICorDebugCode::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c5d42aa7053c1138808775a16d820d5fef3b095
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410824"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="41fe6-102">ICorDebugCode::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="41fe6-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="41fe6-103">Obtiene el tamaño, en bytes, del código binario representado por esta instancia de "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="41fe6-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41fe6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41fe6-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41fe6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41fe6-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="41fe6-106">[out] Un puntero al tamaño, en bytes, del archivo binario de código que este `ICorDebugCode` objeto representa.</span><span class="sxs-lookup"><span data-stu-id="41fe6-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41fe6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41fe6-107">Requirements</span></span>  
 <span data-ttu-id="41fe6-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41fe6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41fe6-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41fe6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41fe6-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41fe6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41fe6-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41fe6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41fe6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="41fe6-112">See Also</span></span>  
 
