---
title: ICorDebugFunction::GetLocalVarSigToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a09741ed778436f1cb35d094885bd3effa813a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411599"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="3f885-102">ICorDebugFunction::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="3f885-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="3f885-103">Obtiene los metadatos del token para la firma de variable local de la función que está representada por esta instancia ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="3f885-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f885-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f885-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f885-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f885-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="3f885-106">[out] Un puntero a la `mdSignature` símbolo (token) de la firma de variable local de esta función, o `mdSignatureNil`, si esta función no tiene variables locales.</span><span class="sxs-lookup"><span data-stu-id="3f885-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f885-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f885-107">Requirements</span></span>  
 <span data-ttu-id="3f885-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f885-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f885-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f885-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f885-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f885-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f885-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f885-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
