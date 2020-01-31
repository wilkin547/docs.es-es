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
ms.openlocfilehash: cc5a2e1de79d6ba04ff3bf2bf86e0cb7ce9a5c0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788390"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="8d27c-102">ICorDebugManagedCallback::LoadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="8d27c-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="8d27c-103">Notifica al depurador que se ha cargado una clase.</span><span class="sxs-lookup"><span data-stu-id="8d27c-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d27c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d27c-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d27c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8d27c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8d27c-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado la clase.</span><span class="sxs-lookup"><span data-stu-id="8d27c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="8d27c-107">de Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="8d27c-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d27c-108">Notas</span><span class="sxs-lookup"><span data-stu-id="8d27c-108">Remarks</span></span>  
 <span data-ttu-id="8d27c-109">Esta devolución de llamada solo se produce si se ha habilitado la carga de clases para el módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="8d27c-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="8d27c-110">La carga de clases está siempre habilitada para los módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="8d27c-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="8d27c-111">La devolución de llamada de `LoadClass` proporciona un tiempo adecuado para enlazar puntos de interrupción a clases recién generadas en módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="8d27c-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d27c-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8d27c-112">Requirements</span></span>  
 <span data-ttu-id="8d27c-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d27c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d27c-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d27c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d27c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d27c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d27c-116">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d27c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d27c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d27c-117">See also</span></span>

- [<span data-ttu-id="8d27c-118">UnloadClass (método)</span><span class="sxs-lookup"><span data-stu-id="8d27c-118">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="8d27c-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d27c-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
