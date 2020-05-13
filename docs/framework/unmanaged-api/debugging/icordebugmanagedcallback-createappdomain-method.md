---
title: ICorDebugManagedCallback::CreateAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
ms.openlocfilehash: 89fba6af9b76f729ca40d4ee63f525611bdf43a9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205645"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="1815e-102">ICorDebugManagedCallback::CreateAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="1815e-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="1815e-103">Notifica al depurador que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1815e-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1815e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1815e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1815e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1815e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="1815e-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso en el que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1815e-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="1815e-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="1815e-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1815e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1815e-108">Requirements</span></span>  
 <span data-ttu-id="1815e-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1815e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1815e-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1815e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1815e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1815e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1815e-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1815e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1815e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1815e-113">See also</span></span>

- [<span data-ttu-id="1815e-114">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1815e-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
