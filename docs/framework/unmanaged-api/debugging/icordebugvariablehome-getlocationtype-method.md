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
ms.openlocfilehash: 5d33c917ab814083ec2f3a3f3de6bdc264d90b77
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791005"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="f027f-102">ICorDebugVariableHome:: GetLocationType (método)</span><span class="sxs-lookup"><span data-stu-id="f027f-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="f027f-103">Obtiene el tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="f027f-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f027f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f027f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f027f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f027f-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="f027f-106">enuncia Puntero al tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="f027f-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="f027f-107">Vea la enumeración [VariableLocationType](variablelocationtype-enumeration.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f027f-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f027f-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f027f-108">Requirements</span></span>  
 <span data-ttu-id="f027f-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f027f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f027f-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f027f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f027f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f027f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f027f-112">**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f027f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f027f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f027f-113">See also</span></span>

- [<span data-ttu-id="f027f-114">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f027f-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="f027f-115">VariableLocationType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="f027f-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
