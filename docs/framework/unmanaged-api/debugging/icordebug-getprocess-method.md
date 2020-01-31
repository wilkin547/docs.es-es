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
ms.openlocfilehash: 2762d0680c5299732196cafe09f6e346e873f19a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785137"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="0eae9-102">ICorDebug::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="0eae9-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="0eae9-103">Obtiene un puntero a la instancia de "ICorDebugProcess" para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="0eae9-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eae9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eae9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eae9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0eae9-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="0eae9-106">de IDENTIFICADOR del proceso.</span><span class="sxs-lookup"><span data-stu-id="0eae9-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="0eae9-107">enuncia Puntero a la dirección de una instancia de `ICorDebugProcess` para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="0eae9-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eae9-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0eae9-108">Requirements</span></span>  
 <span data-ttu-id="0eae9-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eae9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eae9-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eae9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eae9-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eae9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eae9-112">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eae9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eae9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eae9-113">See also</span></span>

- [<span data-ttu-id="0eae9-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0eae9-114">ICorDebug Interface</span></span>](icordebug-interface.md)
