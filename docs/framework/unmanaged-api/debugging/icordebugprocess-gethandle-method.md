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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56f1dd892429724866182248b0c0413a7d2437cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766073"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="72510-102">ICorDebugProcess::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="72510-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="72510-103">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="72510-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72510-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72510-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72510-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72510-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="72510-106">[out] Un puntero a un `HPROCESS` que es el identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="72510-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72510-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72510-107">Remarks</span></span>  
 <span data-ttu-id="72510-108">El identificador recuperado es propiedad de la interfaz de depuración.</span><span class="sxs-lookup"><span data-stu-id="72510-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="72510-109">El depurador debe duplicar el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="72510-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72510-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72510-110">Requirements</span></span>  
 <span data-ttu-id="72510-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72510-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72510-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72510-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72510-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72510-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72510-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72510-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
