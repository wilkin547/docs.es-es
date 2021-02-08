---
description: 'Más información acerca de: ICorDebug:: EnumerateProcesses ((método)'
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
ms.openlocfilehash: 44ee21a820a1c9f94f1d66c93ff040b504bfcc93
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791587"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="6c417-103">ICorDebug::EnumerateProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="6c417-103">ICorDebug::EnumerateProcesses Method</span></span>

<span data-ttu-id="6c417-104">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="6c417-104">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c417-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c417-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c417-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c417-106">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="6c417-107">Puntero a la dirección de un objeto Icordebugprocessenum (que es el enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="6c417-107">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c417-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c417-108">Requirements</span></span>  

 <span data-ttu-id="6c417-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c417-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c417-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c417-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c417-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c417-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c417-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c417-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c417-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c417-113">See also</span></span>

- [<span data-ttu-id="6c417-114">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c417-114">ICorDebug Interface</span></span>](icordebug-interface.md)
