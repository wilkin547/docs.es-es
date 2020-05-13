---
title: ICorDebugManagedCallback::NameChange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
ms.openlocfilehash: 48bfce9966ff12fe1b425fbcd9a81860628a54e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212677"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="0e625-102">ICorDebugManagedCallback::NameChange (Método)</span><span class="sxs-lookup"><span data-stu-id="0e625-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="0e625-103">Notifica al depurador que ha cambiado el nombre de un dominio de aplicación o un subproceso.</span><span class="sxs-lookup"><span data-stu-id="0e625-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e625-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e625-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e625-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e625-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0e625-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que tenía un cambio de nombre o que contiene el subproceso que tenía un cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="0e625-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0e625-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso cuyo nombre ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="0e625-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e625-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e625-108">Requirements</span></span>  
 <span data-ttu-id="0e625-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e625-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e625-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e625-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e625-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e625-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e625-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e625-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e625-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e625-113">See also</span></span>

- [<span data-ttu-id="0e625-114">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e625-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
