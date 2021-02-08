---
description: 'Más información acerca de: ICorDebugManagedCallback:: Createappdomain ((método)'
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
ms.openlocfilehash: 5f4aa49ce90e8ec1343794db71ae3aa911c9e09f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791080"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="a3303-103">ICorDebugManagedCallback::CreateAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="a3303-103">ICorDebugManagedCallback::CreateAppDomain Method</span></span>

<span data-ttu-id="a3303-104">Notifica al depurador que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3303-104">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3303-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3303-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3303-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3303-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="a3303-107">de Un puntero a un objeto ICorDebugProcess que representa el proceso en el que se creó el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3303-107">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a3303-108">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="a3303-108">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3303-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3303-109">Requirements</span></span>  

 <span data-ttu-id="a3303-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3303-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3303-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3303-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3303-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3303-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3303-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3303-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3303-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3303-114">See also</span></span>

- [<span data-ttu-id="a3303-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3303-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
