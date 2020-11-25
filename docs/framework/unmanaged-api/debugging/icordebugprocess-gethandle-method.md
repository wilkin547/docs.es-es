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
ms.openlocfilehash: 87b7b7381ef53f7e2abebc053b5c9f87f94d96c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695080"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="0cabd-102">ICorDebugProcess::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="0cabd-102">ICorDebugProcess::GetHandle Method</span></span>

<span data-ttu-id="0cabd-103">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="0cabd-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cabd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cabd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cabd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0cabd-105">Parameters</span></span>  

 `phProcessHandle`  
 <span data-ttu-id="0cabd-106">enuncia Un puntero a un `HPROCESS` que es el identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="0cabd-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cabd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0cabd-107">Remarks</span></span>  

 <span data-ttu-id="0cabd-108">El identificador recuperado es propiedad de la interfaz de depuración.</span><span class="sxs-lookup"><span data-stu-id="0cabd-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="0cabd-109">El depurador debe duplicar el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="0cabd-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cabd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0cabd-110">Requirements</span></span>  

 <span data-ttu-id="0cabd-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cabd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cabd-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cabd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cabd-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cabd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cabd-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cabd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
