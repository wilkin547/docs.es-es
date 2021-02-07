---
description: 'Más información acerca de: ICorDebugFunction:: GetToken (método)'
title: ICorDebugFunction::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
ms.openlocfilehash: 75c8680252c5047aa7263940da76166597e5a283
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692425"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="6d243-103">ICorDebugFunction::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="6d243-103">ICorDebugFunction::GetToken Method</span></span>

<span data-ttu-id="6d243-104">Obtiene el símbolo (token) de metadatos de esta función.</span><span class="sxs-lookup"><span data-stu-id="6d243-104">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d243-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d243-105">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d243-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d243-106">Parameters</span></span>  

 `pMethodDef`  
 <span data-ttu-id="6d243-107">enuncia Un puntero a un `mdMethodDef` token que hace referencia a los metadatos de esta función.</span><span class="sxs-lookup"><span data-stu-id="6d243-107">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d243-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d243-108">Requirements</span></span>  

 <span data-ttu-id="6d243-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d243-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d243-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d243-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d243-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d243-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d243-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d243-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
