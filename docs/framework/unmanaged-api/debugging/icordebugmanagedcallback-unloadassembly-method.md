---
description: 'Más información acerca de: ICorDebugManagedCallback:: Unloadassembly ((método)'
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
ms.openlocfilehash: b1860e90ba2bab1428a0f8559d18801136bbbb39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660341"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="8a48b-103">ICorDebugManagedCallback::UnloadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="8a48b-103">ICorDebugManagedCallback::UnloadAssembly Method</span></span>

<span data-ttu-id="8a48b-104">Notifica al depurador que se ha descargado un ensamblado de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="8a48b-104">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a48b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a48b-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a48b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a48b-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="8a48b-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8a48b-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="8a48b-108">de Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8a48b-108">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a48b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a48b-109">Remarks</span></span>  

 <span data-ttu-id="8a48b-110">El ensamblado no se debe utilizar después de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="8a48b-110">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a48b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a48b-111">Requirements</span></span>  

 <span data-ttu-id="8a48b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a48b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a48b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a48b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a48b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a48b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a48b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a48b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a48b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a48b-116">See also</span></span>

- [<span data-ttu-id="8a48b-117">Método LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="8a48b-117">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="8a48b-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a48b-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
