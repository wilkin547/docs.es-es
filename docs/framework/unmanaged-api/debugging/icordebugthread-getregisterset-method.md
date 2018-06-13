---
title: ICorDebugThread::GetRegisterSet (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc218370779742055e14dc62a8475c42c344c40c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418739"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="506d7-102">ICorDebugThread::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="506d7-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="506d7-103">Obtiene un puntero de interfaz al conjunto de registros que está asociado a la parte activa de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="506d7-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="506d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="506d7-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="506d7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="506d7-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="506d7-106">[out] Un puntero a la dirección de un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) establece objeto de interfaz que representa el registro para la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="506d7-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="506d7-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="506d7-107">Requirements</span></span>  
 <span data-ttu-id="506d7-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="506d7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="506d7-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="506d7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="506d7-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="506d7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="506d7-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="506d7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
