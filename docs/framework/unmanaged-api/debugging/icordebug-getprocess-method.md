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
ms.openlocfilehash: 64ed875059730e91e28ff0903ab93fb25c68910b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134112"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="53bc7-102">ICorDebug::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="53bc7-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="53bc7-103">Obtiene un puntero a la instancia de "ICorDebugProcess" para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="53bc7-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53bc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53bc7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53bc7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53bc7-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="53bc7-106">de IDENTIFICADOR del proceso.</span><span class="sxs-lookup"><span data-stu-id="53bc7-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="53bc7-107">enuncia Puntero a la dirección de una instancia de `ICorDebugProcess` para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="53bc7-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53bc7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53bc7-108">Requirements</span></span>  
 <span data-ttu-id="53bc7-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53bc7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53bc7-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53bc7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53bc7-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53bc7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53bc7-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53bc7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53bc7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="53bc7-113">See also</span></span>

- [<span data-ttu-id="53bc7-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53bc7-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
