---
title: "ICorDebug::GetProcess (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 189aab8a1e640d822dc8c45098b3af7cb81e916c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="74076-102">ICorDebug::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="74076-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="74076-103">Obtiene un puntero a la instancia de "ICorDebugProcess" para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="74076-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74076-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74076-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74076-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74076-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="74076-106">[in] El identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="74076-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="74076-107">[out] Un puntero a la dirección de un `ICorDebugProcess` instancia para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="74076-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74076-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74076-108">Requirements</span></span>  
 <span data-ttu-id="74076-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74076-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74076-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74076-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74076-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74076-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74076-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74076-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74076-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="74076-113">See Also</span></span>  
 [<span data-ttu-id="74076-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74076-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
