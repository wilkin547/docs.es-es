---
title: ICorDebugModule::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 402a0e8808b51fd4c09b254114292d4c851b2760
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129506"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="6f867-102">ICorDebugModule::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="6f867-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="6f867-103">Obtiene el tamaño, en bytes, del módulo.</span><span class="sxs-lookup"><span data-stu-id="6f867-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f867-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f867-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f867-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f867-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="6f867-106">enuncia Tamaño del módulo en bytes.</span><span class="sxs-lookup"><span data-stu-id="6f867-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="6f867-107">Si el módulo se generó a partir del generador de imágenes nativas (NGen. exe), el tamaño del módulo será cero.</span><span class="sxs-lookup"><span data-stu-id="6f867-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f867-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f867-108">Requirements</span></span>  
 <span data-ttu-id="6f867-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f867-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f867-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f867-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f867-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f867-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f867-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f867-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
