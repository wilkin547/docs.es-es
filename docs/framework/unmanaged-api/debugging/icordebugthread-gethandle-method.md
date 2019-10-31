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
ms.openlocfilehash: 33219d9a67379244e23da49c13617a4c4a2fa66d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133466"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="0e202-102">ICorDebugThread::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="0e202-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="0e202-103">Obtiene el identificador actual para la parte activa de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="0e202-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e202-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e202-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e202-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e202-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="0e202-106">enuncia Un puntero a un HTHREAD que es el identificador de la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="0e202-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e202-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e202-107">Remarks</span></span>  
 <span data-ttu-id="0e202-108">El identificador puede cambiar a medida que se ejecuta el proceso y puede ser diferente para distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="0e202-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="0e202-109">Este identificador es propiedad de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="0e202-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="0e202-110">El depurador debe duplicarlo antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="0e202-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e202-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e202-111">Requirements</span></span>  
 <span data-ttu-id="0e202-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e202-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e202-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e202-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e202-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e202-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e202-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e202-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
