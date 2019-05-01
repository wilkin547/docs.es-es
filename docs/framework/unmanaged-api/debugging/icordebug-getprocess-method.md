---
title: ICorDebug::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dcb869bed71be05e0450580b50dfa9f2a0fca525
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996299"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="a66fd-102">ICorDebug::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="a66fd-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="a66fd-103">Obtiene un puntero a la instancia "ICorDebugProcess" para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="a66fd-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a66fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a66fd-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a66fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a66fd-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="a66fd-106">[in] El identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="a66fd-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a66fd-107">[out] Un puntero a la dirección de un `ICorDebugProcess` instancia para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="a66fd-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a66fd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a66fd-108">Requirements</span></span>  
 <span data-ttu-id="a66fd-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a66fd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a66fd-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a66fd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a66fd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a66fd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a66fd-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a66fd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66fd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a66fd-113">See also</span></span>

- [<span data-ttu-id="a66fd-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a66fd-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
