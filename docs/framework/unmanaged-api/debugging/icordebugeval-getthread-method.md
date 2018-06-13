---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e64bc173717c3121d6c2b101f734ee325a0ced53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413766"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="ecc9b-102">ICorDebugEval::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="ecc9b-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="ecc9b-103">Obtiene el subproceso en el que se está ejecutando o se ejecutará esta evaluación.</span><span class="sxs-lookup"><span data-stu-id="ecc9b-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc9b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecc9b-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecc9b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecc9b-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="ecc9b-106">[out] Un puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ecc9b-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc9b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecc9b-107">Requirements</span></span>  
 <span data-ttu-id="ecc9b-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecc9b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc9b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecc9b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecc9b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecc9b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecc9b-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc9b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
