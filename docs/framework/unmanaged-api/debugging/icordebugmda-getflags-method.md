---
title: ICorDebugMDA::GetFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 38a5c2da900530b6bf78f24e224714496ceaa62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710966"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="2e6aa-102">ICorDebugMDA::GetFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="2e6aa-102">ICorDebugMDA::GetFlags Method</span></span>

<span data-ttu-id="2e6aa-103">Obtiene las marcas asociadas al Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2e6aa-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e6aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e6aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e6aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e6aa-105">Parameters</span></span>  

 `pFlags`  
 <span data-ttu-id="2e6aa-106">de Combinación bit a bit de los valores de enumeración de [CorDebugMDAFlags (](cordebugmdaflags-enumeration.md) que especifican los valores de las marcas para este MDA.</span><span class="sxs-lookup"><span data-stu-id="2e6aa-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e6aa-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e6aa-107">Requirements</span></span>  

 <span data-ttu-id="2e6aa-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e6aa-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e6aa-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e6aa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e6aa-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e6aa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e6aa-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e6aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e6aa-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e6aa-112">See also</span></span>

- [<span data-ttu-id="2e6aa-113">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e6aa-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="2e6aa-114">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="2e6aa-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
