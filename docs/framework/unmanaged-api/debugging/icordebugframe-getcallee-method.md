---
title: ICorDebugFrame::GetCallee (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a179b68e2196eeadc712ae8f7d023b2943533335
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995857"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="af181-102">ICorDebugFrame::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="af181-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="af181-103">Obtiene un puntero al objeto ICorDebugFrame en la cadena actual que llama este marco.</span><span class="sxs-lookup"><span data-stu-id="af181-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af181-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af181-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af181-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af181-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="af181-106">[out] Un puntero a la dirección de un `ICorDebugFrame` objeto que representa el marco de la llamada.</span><span class="sxs-lookup"><span data-stu-id="af181-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="af181-107">Este valor es null si el marco que realiza la llamada es el más interno de la cadena actual.</span><span class="sxs-lookup"><span data-stu-id="af181-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af181-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af181-108">Requirements</span></span>  
 <span data-ttu-id="af181-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af181-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af181-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af181-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af181-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af181-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af181-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af181-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
