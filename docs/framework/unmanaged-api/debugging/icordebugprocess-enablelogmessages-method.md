---
description: 'Más información acerca de: ICorDebugProcess:: Enablelogmessages ((método)'
title: ICorDebugProcess::EnableLogMessages (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
ms.openlocfilehash: d44f1a14611493372c7321feaa14329d5d77b01b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753996"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="dd5ef-103">ICorDebugProcess::EnableLogMessages (Método)</span><span class="sxs-lookup"><span data-stu-id="dd5ef-103">ICorDebugProcess::EnableLogMessages Method</span></span>

<span data-ttu-id="dd5ef-104">Habilita y deshabilita la transmisión de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-104">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd5ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd5ef-105">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd5ef-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd5ef-106">Parameters</span></span>  

 `fOnOff`  
 <span data-ttu-id="dd5ef-107">[in] `true` habilita la transmisión de mensajes de registro; `false` deshabilita la transmisión.</span><span class="sxs-lookup"><span data-stu-id="dd5ef-107">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd5ef-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dd5ef-108">Remarks</span></span>  

 <span data-ttu-id="dd5ef-109">Este método es válido solo después de que se produzca la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dd5ef-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd5ef-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd5ef-110">Requirements</span></span>  

 <span data-ttu-id="dd5ef-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd5ef-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd5ef-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd5ef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd5ef-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd5ef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd5ef-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd5ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
