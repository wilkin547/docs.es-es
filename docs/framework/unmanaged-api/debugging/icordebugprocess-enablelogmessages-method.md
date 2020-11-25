---
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
ms.openlocfilehash: 86cb1a2eb18840419d2a4e8ee4f6475edafe8397
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724629"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="2c5af-102">ICorDebugProcess::EnableLogMessages (Método)</span><span class="sxs-lookup"><span data-stu-id="2c5af-102">ICorDebugProcess::EnableLogMessages Method</span></span>

<span data-ttu-id="2c5af-103">Habilita y deshabilita la transmisión de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="2c5af-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c5af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c5af-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c5af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c5af-105">Parameters</span></span>  

 `fOnOff`  
 <span data-ttu-id="2c5af-106">[in] `true` habilita la transmisión de mensajes de registro; `false` deshabilita la transmisión.</span><span class="sxs-lookup"><span data-stu-id="2c5af-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c5af-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c5af-107">Remarks</span></span>  

 <span data-ttu-id="2c5af-108">Este método es válido solo después de que se produzca la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2c5af-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c5af-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c5af-109">Requirements</span></span>  

 <span data-ttu-id="2c5af-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c5af-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c5af-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c5af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c5af-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c5af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c5af-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c5af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
