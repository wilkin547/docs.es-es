---
title: 'ICorDebugVariableHome:: GetCode (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 4770eb3e93104dd3862eb2163faf1dc7fe9008ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125135"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="cc1db-102">ICorDebugVariableHome:: GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="cc1db-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="cc1db-103">Obtiene la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cc1db-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc1db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc1db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc1db-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc1db-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="cc1db-106">enuncia Puntero a la dirección de la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cc1db-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc1db-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc1db-107">Requirements</span></span>  
 <span data-ttu-id="cc1db-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc1db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc1db-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc1db-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc1db-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc1db-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc1db-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc1db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc1db-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc1db-112">See also</span></span>

- [<span data-ttu-id="cc1db-113">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc1db-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
