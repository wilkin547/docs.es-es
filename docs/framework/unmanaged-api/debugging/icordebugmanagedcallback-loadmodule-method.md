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
ms.openlocfilehash: d13c5be314dc39f3e7b42a8d6b13f6a25751067d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130723"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="63cb6-102">ICorDebugManagedCallback::LoadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="63cb6-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="63cb6-103">Notifica al depurador que un módulo de Common Language Runtime (CLR) se ha cargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="63cb6-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63cb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63cb6-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63cb6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63cb6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="63cb6-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="63cb6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="63cb6-107">de Un puntero a un objeto ICorDebugModule que representa el módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="63cb6-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63cb6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63cb6-108">Remarks</span></span>  
 <span data-ttu-id="63cb6-109">La devolución de llamada de `LoadModule` proporciona un tiempo adecuado para examinar los metadatos del módulo, establecer marcas de compilador Just-in-Time (JIT) o habilitar o deshabilitar las devoluciones de llamada de carga de clases para el módulo.</span><span class="sxs-lookup"><span data-stu-id="63cb6-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63cb6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63cb6-110">Requirements</span></span>  
 <span data-ttu-id="63cb6-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63cb6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63cb6-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63cb6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63cb6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63cb6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63cb6-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63cb6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63cb6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="63cb6-115">See also</span></span>

- [<span data-ttu-id="63cb6-116">UnloadModule (método)</span><span class="sxs-lookup"><span data-stu-id="63cb6-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="63cb6-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63cb6-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
