---
title: ICorDebugThread::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b41c7eeccad8b3f685c81e6afc23eaf19d862182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417617"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="e9ae4-102">ICorDebugThread::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="e9ae4-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="e9ae4-103">Obtiene un puntero de interfaz para el proceso de los cuales este ICorDebugThread constituye una parte.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9ae4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9ae4-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9ae4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9ae4-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="e9ae4-106">[out] Un puntero a la dirección de un objeto de interfaz de ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="e9ae4-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9ae4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9ae4-107">Requirements</span></span>  
 <span data-ttu-id="e9ae4-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9ae4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9ae4-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9ae4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9ae4-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9ae4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9ae4-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ae4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
