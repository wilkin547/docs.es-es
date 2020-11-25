---
title: ICorDebugClass::GetModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
ms.openlocfilehash: e95d10512da73d9f483b87557fd7cd4574503c70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728466"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="5af86-102">ICorDebugClass::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="5af86-102">ICorDebugClass::GetModule Method</span></span>

<span data-ttu-id="5af86-103">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="5af86-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5af86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5af86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5af86-105">Parameters</span></span>  

 `pModule`  
 <span data-ttu-id="5af86-106">enuncia Puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta clase.</span><span class="sxs-lookup"><span data-stu-id="5af86-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5af86-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5af86-107">Requirements</span></span>  

 <span data-ttu-id="5af86-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5af86-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af86-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5af86-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5af86-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5af86-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5af86-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5af86-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
