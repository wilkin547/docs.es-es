---
description: 'Más información acerca de: ICorDebugNativeFrame:: Getregisterset ((método)'
title: ICorDebugNativeFrame::GetRegisterSet (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: 8878c438ad76b1a87429e09b8a4a8bbffb90d00d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722417"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="98f0d-103">ICorDebugNativeFrame::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="98f0d-103">ICorDebugNativeFrame::GetRegisterSet Method</span></span>

<span data-ttu-id="98f0d-104">Obtiene el conjunto de registros para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="98f0d-104">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f0d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98f0d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98f0d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98f0d-106">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="98f0d-107">enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) que representa el conjunto de registros para este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="98f0d-107">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f0d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98f0d-108">Requirements</span></span>  

 <span data-ttu-id="98f0d-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98f0d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98f0d-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98f0d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98f0d-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98f0d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98f0d-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98f0d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f0d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="98f0d-113">See also</span></span>
