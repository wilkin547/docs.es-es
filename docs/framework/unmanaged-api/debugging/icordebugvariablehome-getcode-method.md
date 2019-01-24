---
title: Método ICorDebugVariableHome::GetCode
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 216779ab03b426ceb8003accfbdd182f583b77cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557349"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="c10f8-102">Método ICorDebugVariableHome::GetCode</span><span class="sxs-lookup"><span data-stu-id="c10f8-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="c10f8-103">Obtiene la instancia de "ICorDebugCode" que contiene este [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="c10f8-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c10f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c10f8-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c10f8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c10f8-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="c10f8-106">[out] Un puntero a la dirección de la instancia de "ICorDebugCode" que contiene este [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="c10f8-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c10f8-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c10f8-107">Requirements</span></span>  
 <span data-ttu-id="c10f8-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c10f8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c10f8-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c10f8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c10f8-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c10f8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c10f8-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c10f8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10f8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c10f8-112">See also</span></span>
- [<span data-ttu-id="c10f8-113">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c10f8-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

