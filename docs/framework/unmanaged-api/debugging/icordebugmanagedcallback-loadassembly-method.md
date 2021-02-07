---
description: 'Más información acerca de: ICorDebugManagedCallback:: Loadassembly ((método)'
title: ICorDebugManagedCallback::LoadAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: b90391f3c6286323db11dadae841db38f9b785a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722807"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="32beb-103">ICorDebugManagedCallback::LoadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="32beb-103">ICorDebugManagedCallback::LoadAssembly Method</span></span>

<span data-ttu-id="32beb-104">Notifica al depurador que se ha cargado correctamente un ensamblado Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="32beb-104">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32beb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32beb-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32beb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32beb-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="32beb-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="32beb-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="32beb-108">de Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="32beb-108">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32beb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32beb-109">Requirements</span></span>  

 <span data-ttu-id="32beb-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32beb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32beb-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32beb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32beb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32beb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32beb-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32beb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32beb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="32beb-114">See also</span></span>

- [<span data-ttu-id="32beb-115">Método UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="32beb-115">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="32beb-116">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32beb-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
