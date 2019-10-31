---
title: 'ICorDebugVariableHome:: GetLocationType (método)'
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
ms.openlocfilehash: 1dd4e9510831b4c878e9c1246dabe4add919130c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125108"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="9ddab-102">ICorDebugVariableHome:: GetLocationType (método)</span><span class="sxs-lookup"><span data-stu-id="9ddab-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="9ddab-103">Obtiene el tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="9ddab-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ddab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ddab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ddab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ddab-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="9ddab-106">enuncia Puntero al tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="9ddab-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="9ddab-107">Vea la enumeración [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9ddab-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ddab-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ddab-108">Requirements</span></span>  
 <span data-ttu-id="9ddab-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ddab-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ddab-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ddab-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ddab-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ddab-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ddab-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddab-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ddab-113">See also</span></span>

- [<span data-ttu-id="9ddab-114">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ddab-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="9ddab-115">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="9ddab-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
