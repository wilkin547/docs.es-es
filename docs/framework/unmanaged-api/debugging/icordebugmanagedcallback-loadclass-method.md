---
title: ICorDebugManagedCallback::LoadClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 5d35ab4610ffa04d15dd2404fdf8010308bcb42a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212742"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="879e0-102">ICorDebugManagedCallback::LoadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="879e0-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="879e0-103">Notifica al depurador que se ha cargado una clase.</span><span class="sxs-lookup"><span data-stu-id="879e0-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="879e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="879e0-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="879e0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="879e0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="879e0-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado la clase.</span><span class="sxs-lookup"><span data-stu-id="879e0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="879e0-107">de Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="879e0-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="879e0-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="879e0-108">Remarks</span></span>  
 <span data-ttu-id="879e0-109">Esta devolución de llamada solo se produce si se ha habilitado la carga de clases para el módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="879e0-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="879e0-110">La carga de clases está siempre habilitada para los módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="879e0-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="879e0-111">La `LoadClass` devolución de llamada proporciona un tiempo adecuado para enlazar puntos de interrupción a clases recién generadas en módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="879e0-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="879e0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="879e0-112">Requirements</span></span>  
 <span data-ttu-id="879e0-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="879e0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="879e0-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="879e0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="879e0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="879e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="879e0-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="879e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879e0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="879e0-117">See also</span></span>

- [<span data-ttu-id="879e0-118">Método UnloadClass</span><span class="sxs-lookup"><span data-stu-id="879e0-118">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="879e0-119">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="879e0-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
