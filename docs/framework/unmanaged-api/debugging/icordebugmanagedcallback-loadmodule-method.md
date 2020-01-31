---
title: ICorDebugManagedCallback::LoadModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 21a97f140a41f8f380c1334652bc2417e19659c6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777133"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="c087c-102">ICorDebugManagedCallback::LoadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="c087c-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="c087c-103">Notifica al depurador que un módulo de Common Language Runtime (CLR) se ha cargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c087c-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c087c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c087c-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c087c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c087c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c087c-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="c087c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="c087c-107">de Un puntero a un objeto ICorDebugModule que representa el módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="c087c-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c087c-108">Notas</span><span class="sxs-lookup"><span data-stu-id="c087c-108">Remarks</span></span>  
 <span data-ttu-id="c087c-109">La devolución de llamada de `LoadModule` proporciona un tiempo adecuado para examinar los metadatos del módulo, establecer marcas de compilador Just-in-Time (JIT) o habilitar o deshabilitar las devoluciones de llamada de carga de clases para el módulo.</span><span class="sxs-lookup"><span data-stu-id="c087c-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c087c-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c087c-110">Requirements</span></span>  
 <span data-ttu-id="c087c-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c087c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c087c-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c087c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c087c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c087c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c087c-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c087c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c087c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c087c-115">See also</span></span>

- [<span data-ttu-id="c087c-116">UnloadModule (método)</span><span class="sxs-lookup"><span data-stu-id="c087c-116">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="c087c-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c087c-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
