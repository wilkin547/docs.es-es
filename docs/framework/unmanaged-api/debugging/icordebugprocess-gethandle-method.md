---
description: 'Más información acerca de: ICorDebugProcess:: GetHandle (método)'
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
ms.openlocfilehash: fbc92be53b30d3c70f85fea36e05c6a5514b0f03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722131"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="5d06b-103">ICorDebugProcess::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="5d06b-103">ICorDebugProcess::GetHandle Method</span></span>

<span data-ttu-id="5d06b-104">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="5d06b-104">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d06b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d06b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d06b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d06b-106">Parameters</span></span>  

 `phProcessHandle`  
 <span data-ttu-id="5d06b-107">enuncia Un puntero a un `HPROCESS` que es el identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="5d06b-107">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d06b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5d06b-108">Remarks</span></span>  

 <span data-ttu-id="5d06b-109">El identificador recuperado es propiedad de la interfaz de depuración.</span><span class="sxs-lookup"><span data-stu-id="5d06b-109">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="5d06b-110">El depurador debe duplicar el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="5d06b-110">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d06b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d06b-111">Requirements</span></span>  

 <span data-ttu-id="5d06b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d06b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d06b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d06b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d06b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d06b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d06b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d06b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
