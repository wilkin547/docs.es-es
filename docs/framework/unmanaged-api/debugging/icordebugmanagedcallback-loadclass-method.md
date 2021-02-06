---
description: 'Más información acerca de: ICorDebugManagedCallback:: LoadClass (método)'
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
ms.openlocfilehash: 6f670a2f0798c7edfdc4292334cf9534e59a3007
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660614"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="c2b93-103">ICorDebugManagedCallback::LoadClass (Método)</span><span class="sxs-lookup"><span data-stu-id="c2b93-103">ICorDebugManagedCallback::LoadClass Method</span></span>

<span data-ttu-id="c2b93-104">Notifica al depurador que se ha cargado una clase.</span><span class="sxs-lookup"><span data-stu-id="c2b93-104">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b93-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2b93-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2b93-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2b93-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="c2b93-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se ha cargado la clase.</span><span class="sxs-lookup"><span data-stu-id="c2b93-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="c2b93-108">de Un puntero a un objeto ICorDebugClass que representa la clase.</span><span class="sxs-lookup"><span data-stu-id="c2b93-108">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2b93-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2b93-109">Remarks</span></span>  

 <span data-ttu-id="c2b93-110">Esta devolución de llamada solo se produce si se ha habilitado la carga de clases para el módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="c2b93-110">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="c2b93-111">La carga de clases está siempre habilitada para los módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="c2b93-111">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="c2b93-112">La `LoadClass` devolución de llamada proporciona un tiempo adecuado para enlazar puntos de interrupción a clases recién generadas en módulos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="c2b93-112">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b93-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2b93-113">Requirements</span></span>  

 <span data-ttu-id="c2b93-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2b93-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b93-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2b93-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2b93-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2b93-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2b93-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b93-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b93-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2b93-118">See also</span></span>

- [<span data-ttu-id="c2b93-119">Método UnloadClass</span><span class="sxs-lookup"><span data-stu-id="c2b93-119">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="c2b93-120">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2b93-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
