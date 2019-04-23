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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173152"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="62da8-102">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="62da8-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="62da8-103">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="62da8-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62da8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62da8-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="62da8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62da8-105">Remarks</span></span>  
 <span data-ttu-id="62da8-106">El depurador debe llamar a `Initialize` durante la creación de servicios de tiempo para inicializar la depuración.</span><span class="sxs-lookup"><span data-stu-id="62da8-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="62da8-107">Este método debe llamarse antes que cualquier otro método en `ICorDebug` se llama.</span><span class="sxs-lookup"><span data-stu-id="62da8-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62da8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62da8-108">Requirements</span></span>  
 <span data-ttu-id="62da8-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62da8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62da8-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62da8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62da8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62da8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62da8-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62da8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62da8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="62da8-113">See also</span></span>

- [<span data-ttu-id="62da8-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62da8-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
