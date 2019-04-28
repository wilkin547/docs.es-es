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
ms.openlocfilehash: c5d81564a34ed8e7ef75840e3a174661c36f5411
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994503"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="7eddb-102">ICorDebugProcess::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="7eddb-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="7eddb-103">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="7eddb-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eddb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7eddb-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eddb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7eddb-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="7eddb-106">[out] Un puntero a un `HPROCESS` que es el identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="7eddb-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eddb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7eddb-107">Remarks</span></span>  
 <span data-ttu-id="7eddb-108">El identificador recuperado es propiedad de la interfaz de depuración.</span><span class="sxs-lookup"><span data-stu-id="7eddb-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="7eddb-109">El depurador debe duplicar el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="7eddb-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eddb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7eddb-110">Requirements</span></span>  
 <span data-ttu-id="7eddb-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eddb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eddb-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7eddb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eddb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eddb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eddb-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eddb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
