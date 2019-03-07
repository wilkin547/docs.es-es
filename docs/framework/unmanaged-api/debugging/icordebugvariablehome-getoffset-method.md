---
title: Método ICorDebugVariableHome::GetOffset
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6880584fe407d651010fad885c2dd5983ad4dfcf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492470"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="3b355-102">Método ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="3b355-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="3b355-103">Obtiene el desplazamiento desde el registro de base de una variable.</span><span class="sxs-lookup"><span data-stu-id="3b355-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b355-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b355-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b355-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b355-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="3b355-106">[out] El desplazamiento desde el registro de base.</span><span class="sxs-lookup"><span data-stu-id="3b355-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b355-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b355-107">Return Value</span></span>  
 <span data-ttu-id="3b355-108">El método devuelve los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3b355-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="3b355-109">Valor</span><span class="sxs-lookup"><span data-stu-id="3b355-109">Value</span></span>|<span data-ttu-id="3b355-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b355-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="3b355-111">La variable está en una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="3b355-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="3b355-112">La variable no está en una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="3b355-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b355-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b355-113">Requirements</span></span>  
 <span data-ttu-id="3b355-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b355-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b355-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b355-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b355-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b355-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b355-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b355-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b355-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b355-118">See also</span></span>
- [<span data-ttu-id="3b355-119">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b355-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
