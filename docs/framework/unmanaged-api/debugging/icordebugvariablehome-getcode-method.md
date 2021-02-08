---
description: 'Más información sobre: ICorDebugVariableHome:: GetCode (método)'
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
ms.openlocfilehash: e3ff96816e580fe3cd1cee782dc5bd4166f08a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794642"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="2751c-103">ICorDebugVariableHome:: GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="2751c-103">ICorDebugVariableHome::GetCode Method</span></span>

<span data-ttu-id="2751c-104">Obtiene la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2751c-104">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2751c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2751c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2751c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2751c-106">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="2751c-107">enuncia Puntero a la dirección de la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2751c-107">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2751c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2751c-108">Requirements</span></span>  

 <span data-ttu-id="2751c-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2751c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2751c-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2751c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2751c-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2751c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2751c-112">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2751c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2751c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2751c-113">See also</span></span>

- [<span data-ttu-id="2751c-114">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="2751c-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
