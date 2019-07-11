---
title: ICorDebugChain::GetCallee (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744985"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="a4b97-102">ICorDebugChain::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="a4b97-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="a4b97-103">Obtiene la cadena que se llamó por esta cadena.</span><span class="sxs-lookup"><span data-stu-id="a4b97-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4b97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4b97-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4b97-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="a4b97-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="a4b97-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="a4b97-107">Si esta cadena se está ejecutando (es decir, si esta cadena no está esperando devolver una cadena de llamada), `ppChain` será null.</span><span class="sxs-lookup"><span data-stu-id="a4b97-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4b97-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4b97-108">Remarks</span></span>  
 <span data-ttu-id="a4b97-109">Esta cadena esperará la cadena de llamada devolver antes de que reanuda la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4b97-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="a4b97-110">La cadena de llamada puede estar en otro subproceso en el caso de las llamadas de cálculo de referencias entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a4b97-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b97-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4b97-111">Requirements</span></span>  
 <span data-ttu-id="a4b97-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4b97-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b97-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4b97-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4b97-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4b97-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4b97-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b97-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
