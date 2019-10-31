---
title: ICorDebugProcess::GetHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: e4061580d59b0cf2a6e6e481d5242005e9452caf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128874"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="8571d-102">ICorDebugProcess::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="8571d-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="8571d-103">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="8571d-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8571d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8571d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8571d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8571d-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="8571d-106">enuncia Puntero a un `HPROCESS` que es el identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="8571d-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8571d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8571d-107">Remarks</span></span>  
 <span data-ttu-id="8571d-108">El identificador recuperado es propiedad de la interfaz de depuración.</span><span class="sxs-lookup"><span data-stu-id="8571d-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="8571d-109">El depurador debe duplicar el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="8571d-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8571d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8571d-110">Requirements</span></span>  
 <span data-ttu-id="8571d-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8571d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8571d-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8571d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8571d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8571d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8571d-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8571d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
