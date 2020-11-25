---
title: ICorDebugManagedCallback::UnloadAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: e89b425afb63de8ef496fe545873ce33e5ff828c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724018"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="648ed-102">ICorDebugManagedCallback::UnloadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="648ed-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>

<span data-ttu-id="648ed-103">Notifica al depurador que se ha descargado un ensamblado de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="648ed-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="648ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="648ed-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="648ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="648ed-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="648ed-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="648ed-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="648ed-107">de Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="648ed-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="648ed-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="648ed-108">Remarks</span></span>  

 <span data-ttu-id="648ed-109">El ensamblado no se debe utilizar después de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="648ed-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="648ed-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="648ed-110">Requirements</span></span>  

 <span data-ttu-id="648ed-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="648ed-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="648ed-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="648ed-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="648ed-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="648ed-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="648ed-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="648ed-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648ed-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="648ed-115">See also</span></span>

- [<span data-ttu-id="648ed-116">Método LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="648ed-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="648ed-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="648ed-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
