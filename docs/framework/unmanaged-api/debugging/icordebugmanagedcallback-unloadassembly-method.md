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
ms.openlocfilehash: 07996a78d7f559de587c8a3eb2babfc06675169d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212651"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="1ff5b-102">ICorDebugManagedCallback::UnloadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="1ff5b-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="1ff5b-103">Notifica al depurador que se ha descargado un ensamblado de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1ff5b-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ff5b-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ff5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ff5b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1ff5b-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1ff5b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="1ff5b-107">de Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1ff5b-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ff5b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ff5b-108">Remarks</span></span>  
 <span data-ttu-id="1ff5b-109">El ensamblado no se debe utilizar después de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1ff5b-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ff5b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ff5b-110">Requirements</span></span>  
 <span data-ttu-id="1ff5b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ff5b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ff5b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ff5b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ff5b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ff5b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ff5b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ff5b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff5b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ff5b-115">See also</span></span>

- [<span data-ttu-id="1ff5b-116">Método LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="1ff5b-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="1ff5b-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ff5b-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
