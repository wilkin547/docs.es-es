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
ms.openlocfilehash: 6a4cadae7a43d0cd965e51535eae2c95e59900d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130018"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="c8d38-102">Método ICorDebugVariableHome::GetCode</span><span class="sxs-lookup"><span data-stu-id="c8d38-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="c8d38-103">Obtiene la instancia de "ICorDebugCode" que contiene este [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="c8d38-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8d38-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8d38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8d38-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="c8d38-106">[out] Un puntero a la dirección de la instancia de "ICorDebugCode" que contiene este [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="c8d38-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8d38-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8d38-107">Requirements</span></span>  
 <span data-ttu-id="c8d38-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8d38-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8d38-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8d38-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8d38-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8d38-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8d38-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8d38-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d38-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8d38-112">See also</span></span>

- [<span data-ttu-id="c8d38-113">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8d38-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
