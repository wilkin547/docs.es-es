---
description: 'Más información acerca de: ICorDebugProcess:: GetThread ((método)'
title: ICorDebugProcess::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
ms.openlocfilehash: bd636df50afd3f12901c1b48559c44ac6ad0cb81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746911"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="3765e-103">ICorDebugProcess::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="3765e-103">ICorDebugProcess::GetThread Method</span></span>

<span data-ttu-id="3765e-104">Obtiene el subproceso de este proceso que tiene el identificador de subproceso del sistema operativo (SO) especificado.</span><span class="sxs-lookup"><span data-stu-id="3765e-104">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3765e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3765e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3765e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3765e-106">Parameters</span></span>  

 `dwThreadId`  
 <span data-ttu-id="3765e-107">de IDENTIFICADOR del subproceso del sistema operativo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="3765e-107">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="3765e-108">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="3765e-108">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3765e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3765e-109">Requirements</span></span>  

 <span data-ttu-id="3765e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3765e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3765e-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3765e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3765e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3765e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3765e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3765e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
