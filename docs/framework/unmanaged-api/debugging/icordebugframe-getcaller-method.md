---
description: 'Más información sobre: ICorDebugFrame:: GetCaller ((método)'
title: ICorDebugFrame::GetCaller (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: a042341f6edfa0e8f6ca00f758107852f9e381cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693049"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="8f781-103">ICorDebugFrame::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="8f781-103">ICorDebugFrame::GetCaller Method</span></span>

<span data-ttu-id="8f781-104">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual que llamó a este marco.</span><span class="sxs-lookup"><span data-stu-id="8f781-104">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f781-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f781-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f781-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f781-106">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="8f781-107">enuncia Puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="8f781-107">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="8f781-108">Este valor es NULL si el marco llamado es el marco más externo de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="8f781-108">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f781-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f781-109">Requirements</span></span>  

 <span data-ttu-id="8f781-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f781-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f781-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f781-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f781-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f781-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f781-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f781-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
