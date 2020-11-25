---
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
ms.openlocfilehash: 6efd451c6895e8fef443e2e86afa6e98279c6493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724005"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="81cf9-102">ICorDebugManagedCallback::UnloadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="81cf9-102">ICorDebugManagedCallback::UnloadClass Method</span></span>

<span data-ttu-id="81cf9-103">Notifica al depurador que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="81cf9-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81cf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81cf9-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81cf9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81cf9-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="81cf9-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="81cf9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="81cf9-107">de Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="81cf9-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81cf9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81cf9-108">Remarks</span></span>  

 <span data-ttu-id="81cf9-109">No se debe hacer referencia a la clase después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="81cf9-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81cf9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81cf9-110">Requirements</span></span>  

 <span data-ttu-id="81cf9-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81cf9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81cf9-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81cf9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81cf9-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81cf9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81cf9-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81cf9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81cf9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81cf9-115">See also</span></span>

- [<span data-ttu-id="81cf9-116">Método LoadClass</span><span class="sxs-lookup"><span data-stu-id="81cf9-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="81cf9-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81cf9-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
