---
description: 'Más información acerca de: ICorDebugEval:: GetThread ((método)'
title: ICorDebugEval::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: 3e7120f618abce31b9940a886fd6b2b2f8639d2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694154"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="4fdab-103">ICorDebugEval::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="4fdab-103">ICorDebugEval::GetThread Method</span></span>

<span data-ttu-id="4fdab-104">Obtiene el subproceso en el que se ejecuta esta evaluación o que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="4fdab-104">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fdab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fdab-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fdab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fdab-106">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="4fdab-107">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="4fdab-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fdab-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fdab-108">Requirements</span></span>  

 <span data-ttu-id="4fdab-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fdab-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fdab-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fdab-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fdab-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fdab-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fdab-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fdab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
