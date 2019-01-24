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
ms.openlocfilehash: 687c3bb441c2a12529c873b4fa5f9283b9326a40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659074"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="ecf44-102">Método ICorDebugVariableHome::GetOffset</span><span class="sxs-lookup"><span data-stu-id="ecf44-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="ecf44-103">Obtiene el desplazamiento desde el registro de base de una variable.</span><span class="sxs-lookup"><span data-stu-id="ecf44-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf44-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecf44-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecf44-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecf44-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="ecf44-106">[out] El desplazamiento desde el registro de base.</span><span class="sxs-lookup"><span data-stu-id="ecf44-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecf44-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ecf44-107">Return Value</span></span>  
 <span data-ttu-id="ecf44-108">El método devuelve los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecf44-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="ecf44-109">Valor</span><span class="sxs-lookup"><span data-stu-id="ecf44-109">Value</span></span>|<span data-ttu-id="ecf44-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecf44-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ecf44-111">La variable está en una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="ecf44-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ecf44-112">La variable no está en una ubicación de memoria relativa del registro.</span><span class="sxs-lookup"><span data-stu-id="ecf44-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ecf44-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecf44-113">Requirements</span></span>  
 <span data-ttu-id="ecf44-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecf44-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecf44-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecf44-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecf44-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecf44-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecf44-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecf44-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf44-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecf44-118">See also</span></span>
- [<span data-ttu-id="ecf44-119">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ecf44-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
