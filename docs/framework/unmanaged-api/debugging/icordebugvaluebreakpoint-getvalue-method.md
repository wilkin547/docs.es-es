---
description: 'Más información sobre: Icordebugvaluebreakpoint (:: GetValue (método)'
title: ICorDebugValueBreakpoint::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
ms.openlocfilehash: b690ea7a39ac70edd8e3e6be7682bae1e808555d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690176"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="17fe6-103">ICorDebugValueBreakpoint::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="17fe6-103">ICorDebugValueBreakpoint::GetValue Method</span></span>

<span data-ttu-id="17fe6-104">Obtiene un puntero de interfaz a un objeto "ICorDebugValue" que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="17fe6-104">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17fe6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17fe6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17fe6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17fe6-106">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="17fe6-107">enuncia Puntero a la dirección de un `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="17fe6-107">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17fe6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17fe6-108">Requirements</span></span>  

 <span data-ttu-id="17fe6-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17fe6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17fe6-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17fe6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17fe6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17fe6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17fe6-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17fe6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fe6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="17fe6-113">See also</span></span>
