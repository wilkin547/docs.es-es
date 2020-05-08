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
ms.openlocfilehash: 59afc8ae7d66e81e4dca3923f9c6f7ff3a3a6605
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895386"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="1c088-102">ICorDebug::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="1c088-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="1c088-103">Obtiene un puntero a la instancia de "ICorDebugProcess" para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="1c088-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c088-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c088-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c088-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c088-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="1c088-106">de IDENTIFICADOR del proceso.</span><span class="sxs-lookup"><span data-stu-id="1c088-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="1c088-107">enuncia Puntero a la dirección de una `ICorDebugProcess` instancia para el proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="1c088-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c088-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c088-108">Requirements</span></span>  
 <span data-ttu-id="1c088-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c088-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c088-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c088-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c088-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c088-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c088-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c088-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c088-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1c088-113">See also</span></span>

- [<span data-ttu-id="1c088-114">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c088-114">ICorDebug Interface</span></span>](icordebug-interface.md)
