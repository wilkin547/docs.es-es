---
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
ms.openlocfilehash: 33a68d11a8d17e46533b4f83bbf87aafe171e612
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212404"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="f309f-102">ICorDebugManagedCallback::ControlCTrap (Método)</span><span class="sxs-lookup"><span data-stu-id="f309f-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="f309f-103">Notifica al depurador que se ha capturado CTRL + C en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="f309f-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f309f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f309f-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f309f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f309f-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="f309f-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso en el que se intercepta CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="f309f-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f309f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f309f-107">Return Value</span></span>  
  
|<span data-ttu-id="f309f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f309f-108">HRESULT</span></span>|<span data-ttu-id="f309f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f309f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f309f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f309f-110">S_OK</span></span>|<span data-ttu-id="f309f-111">El depurador controlará la captura CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="f309f-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="f309f-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f309f-112">S_FALSE</span></span>|<span data-ttu-id="f309f-113">El depurador no controlará la captura CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="f309f-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f309f-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f309f-114">Remarks</span></span>  
 <span data-ttu-id="f309f-115">Todos los dominios de aplicación dentro del proceso se detienen para esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f309f-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f309f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f309f-116">Requirements</span></span>  
 <span data-ttu-id="f309f-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f309f-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f309f-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f309f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f309f-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f309f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f309f-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f309f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f309f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f309f-121">See also</span></span>

- [<span data-ttu-id="f309f-122">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f309f-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
