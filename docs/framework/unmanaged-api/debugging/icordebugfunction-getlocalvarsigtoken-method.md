---
description: 'Más información acerca de: ICorDebugFunction:: Getlocalvarsigtoken ((método)'
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
ms.openlocfilehash: cd7fb03829285ddcb1da2f1a93985fa1f98d3d39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692503"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="d4ee9-103">ICorDebugFunction::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="d4ee9-103">ICorDebugFunction::GetLocalVarSigToken Method</span></span>

<span data-ttu-id="d4ee9-104">Obtiene el símbolo (token) de metadatos de la firma de variable local de la función representada por esta instancia de ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="d4ee9-104">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4ee9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4ee9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4ee9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4ee9-106">Parameters</span></span>  

 `pmdSig`  
 <span data-ttu-id="d4ee9-107">enuncia Un puntero al `mdSignature` token para la firma de variable local de esta función, o bien `mdSignatureNil` , si esta función no tiene ninguna variable local.</span><span class="sxs-lookup"><span data-stu-id="d4ee9-107">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4ee9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4ee9-108">Requirements</span></span>  

 <span data-ttu-id="d4ee9-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4ee9-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4ee9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4ee9-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4ee9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4ee9-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4ee9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
