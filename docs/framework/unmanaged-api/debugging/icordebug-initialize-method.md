---
title: "ICorDebug::Initialize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.Initialize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12665472b201e6d89be9c5cc6c78b82de067d6a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="afee7-102">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="afee7-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="afee7-103">Inicializa el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="afee7-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afee7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afee7-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="afee7-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="afee7-105">Remarks</span></span>  
 <span data-ttu-id="afee7-106">El depurador debe llamar a `Initialize` durante la creación de servicios de tiempo para inicializar la depuración.</span><span class="sxs-lookup"><span data-stu-id="afee7-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="afee7-107">Este método se debe llamar antes de cualquier otro método en `ICorDebug` se llama.</span><span class="sxs-lookup"><span data-stu-id="afee7-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afee7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afee7-108">Requirements</span></span>  
 <span data-ttu-id="afee7-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afee7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afee7-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afee7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afee7-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afee7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afee7-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afee7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afee7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="afee7-113">See Also</span></span>  
 [<span data-ttu-id="afee7-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="afee7-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
