---
title: ICorDebugThread::GetHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994024"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="953e1-102">ICorDebugThread::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="953e1-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="953e1-103">Obtiene el identificador actual para la parte activa de este ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="953e1-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="953e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="953e1-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="953e1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="953e1-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="953e1-106">[out] Un puntero a HTHREAD que es el identificador de la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="953e1-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="953e1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="953e1-107">Remarks</span></span>  
 <span data-ttu-id="953e1-108">El identificador puede cambiar cuando se ejecuta el proceso y puede ser diferente para las distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="953e1-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="953e1-109">Este identificador pertenece a la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="953e1-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="953e1-110">El depurador debe duplicarlo antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="953e1-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953e1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="953e1-111">Requirements</span></span>  
 <span data-ttu-id="953e1-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="953e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="953e1-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="953e1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="953e1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="953e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="953e1-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="953e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
