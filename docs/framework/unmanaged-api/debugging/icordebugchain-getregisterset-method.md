---
description: 'Más información sobre: ICorDebugChain:: Getregisterset ((método)'
title: ICorDebugChain::GetRegisterSet (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: 75c77838cb4ef49dd922a4e39b41e622693e928d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694961"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="b6dd8-103">ICorDebugChain::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="b6dd8-103">ICorDebugChain::GetRegisterSet Method</span></span>

<span data-ttu-id="b6dd8-104">Obtiene el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="b6dd8-104">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6dd8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6dd8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6dd8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6dd8-106">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="b6dd8-107">enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="b6dd8-107">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6dd8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6dd8-108">Requirements</span></span>  

 <span data-ttu-id="b6dd8-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6dd8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6dd8-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6dd8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6dd8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6dd8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6dd8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6dd8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
