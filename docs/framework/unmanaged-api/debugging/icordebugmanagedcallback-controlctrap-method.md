---
description: 'Más información acerca de: ICorDebugManagedCallback:: ControlCTrap ((método)'
title: ICorDebugManagedCallback::ControlCTrap (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
ms.openlocfilehash: 9fa71dacb20ff6df21d8aabb687c2601f27643c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791075"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="e26af-103">ICorDebugManagedCallback::ControlCTrap (Método)</span><span class="sxs-lookup"><span data-stu-id="e26af-103">ICorDebugManagedCallback::ControlCTrap Method</span></span>

<span data-ttu-id="e26af-104">Notifica al depurador que se ha capturado CTRL + C en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="e26af-104">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e26af-105">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e26af-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e26af-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="e26af-107">de Un puntero a un objeto ICorDebugProcess que representa el proceso en el que se intercepta CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="e26af-107">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e26af-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e26af-108">Return Value</span></span>  
  
|<span data-ttu-id="e26af-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e26af-109">HRESULT</span></span>|<span data-ttu-id="e26af-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e26af-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e26af-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e26af-111">S_OK</span></span>|<span data-ttu-id="e26af-112">El depurador controlará la captura CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="e26af-112">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="e26af-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e26af-113">S_FALSE</span></span>|<span data-ttu-id="e26af-114">El depurador no controlará la captura CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="e26af-114">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e26af-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e26af-115">Remarks</span></span>  

 <span data-ttu-id="e26af-116">Todos los dominios de aplicación dentro del proceso se detienen para esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e26af-116">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e26af-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e26af-117">Requirements</span></span>  

 <span data-ttu-id="e26af-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e26af-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e26af-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e26af-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e26af-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e26af-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e26af-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e26af-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26af-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e26af-122">See also</span></span>

- [<span data-ttu-id="e26af-123">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e26af-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
