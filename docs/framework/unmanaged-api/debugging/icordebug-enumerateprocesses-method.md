---
title: ICorDebug::EnumerateProcesses (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
ms.openlocfilehash: c2a176764332eed6affda704c8bfaf546ef70880
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789001"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="e0c3a-102">ICorDebug::EnumerateProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="e0c3a-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="e0c3a-103">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="e0c3a-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0c3a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c3a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="e0c3a-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="e0c3a-106">Puntero a la dirección de un objeto Icordebugprocessenum (que es el enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="e0c3a-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c3a-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e0c3a-107">Requirements</span></span>  
 <span data-ttu-id="e0c3a-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0c3a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c3a-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0c3a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0c3a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0c3a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0c3a-111">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c3a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c3a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0c3a-112">See also</span></span>

- [<span data-ttu-id="e0c3a-113">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0c3a-113">ICorDebug Interface</span></span>](icordebug-interface.md)
