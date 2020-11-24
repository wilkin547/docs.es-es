---
title: ICorDebugManagedCallback::ExitThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
ms.openlocfilehash: 2ccb06b974cb17dff987ba42b647224cdc4c4ff2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688961"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="f6f05-102">ICorDebugManagedCallback::ExitThread (Método)</span><span class="sxs-lookup"><span data-stu-id="f6f05-102">ICorDebugManagedCallback::ExitThread Method</span></span>

<span data-ttu-id="f6f05-103">Notifica al depurador que un subproceso que estaba ejecutando código administrado ha salido.</span><span class="sxs-lookup"><span data-stu-id="f6f05-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6f05-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6f05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6f05-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="f6f05-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="f6f05-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="f6f05-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="f6f05-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6f05-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6f05-108">Remarks</span></span>  

 <span data-ttu-id="f6f05-109">Una vez que `ExitThread` se activa la devolución de llamada, el subproceso ya no aparecerá en las enumeraciones de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f6f05-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6f05-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6f05-110">Requirements</span></span>  

 <span data-ttu-id="f6f05-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6f05-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6f05-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6f05-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6f05-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6f05-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6f05-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6f05-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f05-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6f05-115">See also</span></span>

- [<span data-ttu-id="f6f05-116">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6f05-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
