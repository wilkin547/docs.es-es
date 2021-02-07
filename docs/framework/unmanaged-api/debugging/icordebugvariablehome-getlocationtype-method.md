---
description: 'Más información sobre: ICorDebugVariableHome:: GetLocationType (método)'
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
ms.openlocfilehash: 6efe9c045641d162be820961ca75c21a2b8fc14b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728800"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="841b0-103">ICorDebugVariableHome:: GetLocationType (método)</span><span class="sxs-lookup"><span data-stu-id="841b0-103">ICorDebugVariableHome::GetLocationType Method</span></span>

<span data-ttu-id="841b0-104">Obtiene el tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="841b0-104">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="841b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="841b0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="841b0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="841b0-106">Parameters</span></span>  

 `pLocationType`  
 <span data-ttu-id="841b0-107">enuncia Puntero al tipo de la ubicación nativa de la variable.</span><span class="sxs-lookup"><span data-stu-id="841b0-107">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="841b0-108">Vea la enumeración [VariableLocationType](variablelocationtype-enumeration.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="841b0-108">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="841b0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="841b0-109">Requirements</span></span>  

 <span data-ttu-id="841b0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="841b0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="841b0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="841b0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="841b0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="841b0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="841b0-113">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="841b0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841b0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="841b0-114">See also</span></span>

- [<span data-ttu-id="841b0-115">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="841b0-115">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="841b0-116">Enumeración VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="841b0-116">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)
