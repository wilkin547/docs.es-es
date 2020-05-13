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
ms.openlocfilehash: a923701b05f7d283c4fd464d470fb0c9243c1bd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213613"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="acd12-102">ICorDebugFunction::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="acd12-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="acd12-103">Obtiene el símbolo (token) de metadatos de la firma de variable local de la función representada por esta instancia de ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="acd12-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acd12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acd12-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acd12-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="acd12-106">enuncia Un puntero al `mdSignature` token para la firma de variable local de esta función, o bien `mdSignatureNil` , si esta función no tiene ninguna variable local.</span><span class="sxs-lookup"><span data-stu-id="acd12-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acd12-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acd12-107">Requirements</span></span>  
 <span data-ttu-id="acd12-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acd12-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acd12-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acd12-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acd12-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acd12-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acd12-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acd12-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
