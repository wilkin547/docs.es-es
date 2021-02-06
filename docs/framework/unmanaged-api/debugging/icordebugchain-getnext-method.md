---
description: 'Más información acerca de: ICorDebugChain:: GetNext (método)'
title: ICorDebugChain::GetNext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
ms.openlocfilehash: ced7032feffa4c14c07341242b854c08b8c897a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661329"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="ad676-103">ICorDebugChain::GetNext (Método)</span><span class="sxs-lookup"><span data-stu-id="ad676-103">ICorDebugChain::GetNext Method</span></span>

<span data-ttu-id="ad676-104">Obtiene la cadena de fotogramas siguiente para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ad676-104">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad676-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad676-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad676-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad676-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="ad676-107">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena de fotogramas siguiente para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ad676-107">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="ad676-108">Si esta cadena es la última cadena, `ppChain` es NULL.</span><span class="sxs-lookup"><span data-stu-id="ad676-108">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad676-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad676-109">Requirements</span></span>  

 <span data-ttu-id="ad676-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad676-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad676-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad676-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad676-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad676-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad676-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad676-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
