---
title: ICorDebugFrame::GetCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca64e392b930ed57691f05ae771bbaf305df8eb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754077"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="74b01-102">ICorDebugFrame::GetCode (Método)</span><span class="sxs-lookup"><span data-stu-id="74b01-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="74b01-103">Obtiene un puntero al código asociado con este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="74b01-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74b01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74b01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74b01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74b01-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="74b01-106">[out] Un puntero a la dirección de un objeto ICorDebugCode que representa el código asociado a este marco.</span><span class="sxs-lookup"><span data-stu-id="74b01-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74b01-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74b01-107">Requirements</span></span>  
 <span data-ttu-id="74b01-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74b01-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74b01-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74b01-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74b01-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74b01-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74b01-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74b01-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
