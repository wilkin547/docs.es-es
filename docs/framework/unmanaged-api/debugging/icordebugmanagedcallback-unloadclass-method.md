---
description: 'Más información acerca de: ICorDebugManagedCallback:: UnloadClass ((método)'
title: ICorDebugManagedCallback::UnloadClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: b76caf39611b0f59c74b4ae47d167e6f232a6dbc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660224"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="365b6-103">ICorDebugManagedCallback::UnloadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="365b6-103">ICorDebugManagedCallback::UnloadClass Method</span></span>

<span data-ttu-id="365b6-104">Notifica al depurador que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="365b6-104">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="365b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="365b6-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="365b6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="365b6-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="365b6-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="365b6-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="365b6-108">de Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="365b6-108">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="365b6-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="365b6-109">Remarks</span></span>  

 <span data-ttu-id="365b6-110">No se debe hacer referencia a la clase después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="365b6-110">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="365b6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="365b6-111">Requirements</span></span>  

 <span data-ttu-id="365b6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="365b6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="365b6-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="365b6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="365b6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="365b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="365b6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="365b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="365b6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="365b6-116">See also</span></span>

- [<span data-ttu-id="365b6-117">Método LoadClass</span><span class="sxs-lookup"><span data-stu-id="365b6-117">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="365b6-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="365b6-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
