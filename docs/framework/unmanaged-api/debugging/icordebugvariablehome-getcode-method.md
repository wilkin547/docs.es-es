---
title: 'ICorDebugVariableHome:: GetCode (método)'
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
ms.openlocfilehash: 6f5d99e6dc4290ef69c0a0748fe15ae538e83558
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684231"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="6c28e-102">ICorDebugVariableHome:: GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="6c28e-102">ICorDebugVariableHome::GetCode Method</span></span>

<span data-ttu-id="6c28e-103">Obtiene la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6c28e-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c28e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c28e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c28e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c28e-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="6c28e-106">enuncia Puntero a la dirección de la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6c28e-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c28e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c28e-107">Requirements</span></span>  

 <span data-ttu-id="6c28e-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c28e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c28e-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c28e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c28e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c28e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c28e-111">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c28e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c28e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c28e-112">See also</span></span>

- [<span data-ttu-id="6c28e-113">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="6c28e-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
