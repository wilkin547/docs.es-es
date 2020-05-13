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
ms.openlocfilehash: 606453424d34dcb22716c308d210fb257d1c37a7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378865"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="6328b-102">ICorDebugThread::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="6328b-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="6328b-103">Obtiene un puntero de interfaz al conjunto de registros asociado a la parte activa de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="6328b-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6328b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6328b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6328b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6328b-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="6328b-106">enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface que representa el conjunto de registros para la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="6328b-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6328b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6328b-107">Requirements</span></span>  
 <span data-ttu-id="6328b-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6328b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6328b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6328b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6328b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6328b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6328b-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6328b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
