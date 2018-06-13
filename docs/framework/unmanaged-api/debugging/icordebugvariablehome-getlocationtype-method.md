---
title: ICorDebugVariableHome::GetLocationType (método)
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c04fa944f2a3da9b6548ada36443d5dda4725f21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421135"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="d4f48-102">ICorDebugVariableHome::GetLocationType (método)</span><span class="sxs-lookup"><span data-stu-id="d4f48-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="d4f48-103">Obtiene el tipo de ubicación de la variable nativo.</span><span class="sxs-lookup"><span data-stu-id="d4f48-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f48-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4f48-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4f48-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4f48-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="d4f48-106">[out] Un puntero al tipo de ubicación de la variable nativo.</span><span class="sxs-lookup"><span data-stu-id="d4f48-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="d4f48-107">Consulte la [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeración para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d4f48-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f48-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4f48-108">Requirements</span></span>  
 <span data-ttu-id="d4f48-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4f48-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f48-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4f48-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4f48-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4f48-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4f48-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f48-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f48-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4f48-113">See Also</span></span>  
 [<span data-ttu-id="d4f48-114">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4f48-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="d4f48-115">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="d4f48-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
