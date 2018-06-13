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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53d40c198b53370733009c76fd3d49f14df93e6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402101"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="c1c51-102">ICorDebug::EnumerateProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="c1c51-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="c1c51-103">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="c1c51-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1c51-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1c51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1c51-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="c1c51-106">Un puntero a la dirección de un objeto ICorDebugProcessEnum que es el enumerador para los procesos que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="c1c51-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c51-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1c51-107">Requirements</span></span>  
 <span data-ttu-id="c1c51-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c51-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c51-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1c51-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1c51-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1c51-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1c51-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c51-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c51-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1c51-112">See Also</span></span>  
 [<span data-ttu-id="c1c51-113">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1c51-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
