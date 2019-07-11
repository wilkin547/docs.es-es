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
ms.openlocfilehash: 8769293364c111754f4bfe9360a0dca93c0ba13c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770607"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="7a8fe-102">ICorDebugThread::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="7a8fe-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="7a8fe-103">Obtiene un puntero de interfaz al conjunto de registros que está asociado a la parte activa de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a8fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a8fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a8fe-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="7a8fe-106">[out] Un puntero a la dirección de un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) establece el objeto de interfaz que representa el registro para la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="7a8fe-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8fe-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a8fe-107">Requirements</span></span>  
 <span data-ttu-id="7a8fe-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a8fe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a8fe-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a8fe-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a8fe-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a8fe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a8fe-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a8fe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
