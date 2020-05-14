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
ms.openlocfilehash: 8874deede8b46b93df0e298fb3970fa153b51415
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396573"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="adae2-102">ICorDebugVariableHome:: GetLocationType (método)</span><span class="sxs-lookup"><span data-stu-id="adae2-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="adae2-103">Obtiene el tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="adae2-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adae2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adae2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adae2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="adae2-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="adae2-106">enuncia Puntero al tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="adae2-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="adae2-107">Vea la enumeración [VariableLocationType](variablelocationtype-enumeration.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="adae2-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adae2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="adae2-108">Requirements</span></span>  
 <span data-ttu-id="adae2-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adae2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adae2-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adae2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adae2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adae2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adae2-112">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adae2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adae2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="adae2-113">See also</span></span>

- [<span data-ttu-id="adae2-114">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="adae2-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="adae2-115">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="adae2-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
