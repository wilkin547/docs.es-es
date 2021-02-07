---
description: 'Más información acerca de: ICorDebugBoxValue (:: GetObject (método)'
title: ICorDebugBoxValue::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
ms.openlocfilehash: fc5376fa7ddbbeae3464427b34caf991d0a2f59a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711869"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="e0e51-103">ICorDebugBoxValue::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="e0e51-103">ICorDebugBoxValue::GetObject Method</span></span>

<span data-ttu-id="e0e51-104">Obtiene el valor de la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e0e51-104">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0e51-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0e51-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0e51-106">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="e0e51-107">enuncia Puntero a la dirección de un objeto ICorDebugObjectValue que representa el valor de la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e0e51-107">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e51-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0e51-108">Requirements</span></span>  

 <span data-ttu-id="e0e51-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0e51-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0e51-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0e51-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0e51-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0e51-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0e51-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0e51-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
