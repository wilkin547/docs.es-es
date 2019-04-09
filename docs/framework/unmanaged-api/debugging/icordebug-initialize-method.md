---
title: ICorDebug::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd09ce27c0fea9dca8fd86afc563651d68542e13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173152"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="30e73-102">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="30e73-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="30e73-103">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="30e73-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30e73-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="30e73-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30e73-105">Remarks</span></span>  
 <span data-ttu-id="30e73-106">El depurador debe llamar a `Initialize` durante la creación de servicios de tiempo para inicializar la depuración.</span><span class="sxs-lookup"><span data-stu-id="30e73-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="30e73-107">Este método debe llamarse antes que cualquier otro método en `ICorDebug` se llama.</span><span class="sxs-lookup"><span data-stu-id="30e73-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30e73-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30e73-108">Requirements</span></span>  
 <span data-ttu-id="30e73-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30e73-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30e73-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30e73-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30e73-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30e73-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="30e73-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="30e73-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30e73-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e73-113">See also</span></span>

- [<span data-ttu-id="30e73-114">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30e73-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
