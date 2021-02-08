---
description: 'Más información acerca de: ICorDebugMDA:: GetFlags (método)'
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
ms.openlocfilehash: 53476da06252771627d4883ef9056eb7f945e1b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801181"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="393c2-103">ICorDebugMDA::GetFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="393c2-103">ICorDebugMDA::GetFlags Method</span></span>

<span data-ttu-id="393c2-104">Obtiene las marcas asociadas al Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="393c2-104">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="393c2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="393c2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="393c2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="393c2-106">Parameters</span></span>  

 `pFlags`  
 <span data-ttu-id="393c2-107">de Combinación bit a bit de los valores de enumeración de [CorDebugMDAFlags (](cordebugmdaflags-enumeration.md) que especifican los valores de las marcas para este MDA.</span><span class="sxs-lookup"><span data-stu-id="393c2-107">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="393c2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="393c2-108">Requirements</span></span>  

 <span data-ttu-id="393c2-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="393c2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="393c2-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="393c2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="393c2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="393c2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="393c2-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="393c2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="393c2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="393c2-113">See also</span></span>

- [<span data-ttu-id="393c2-114">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="393c2-114">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="393c2-115">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="393c2-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
