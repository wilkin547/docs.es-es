---
description: 'Más información acerca de: ICorDebugThread:: Getregisterset ((método)'
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
ms.openlocfilehash: f61ccb34eabc1f4d8b8db8a0b78e3ddde9aa136d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658911"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="f2704-103">ICorDebugThread::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="f2704-103">ICorDebugThread::GetRegisterSet Method</span></span>

<span data-ttu-id="f2704-104">Obtiene un puntero de interfaz al conjunto de registros asociado a la parte activa de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f2704-104">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2704-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2704-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2704-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2704-106">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="f2704-107">enuncia Puntero a la dirección de un objeto [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface que representa el conjunto de registros para la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="f2704-107">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2704-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2704-108">Requirements</span></span>  

 <span data-ttu-id="f2704-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2704-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2704-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2704-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2704-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2704-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2704-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2704-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
