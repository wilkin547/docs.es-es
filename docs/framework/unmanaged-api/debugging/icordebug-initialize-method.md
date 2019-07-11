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
ms.openlocfilehash: 80465c8d1f1f9e09c0675de1667b999b332b9f6b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738149"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="72abe-102">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="72abe-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="72abe-103">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="72abe-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72abe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72abe-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="72abe-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72abe-105">Remarks</span></span>  
 <span data-ttu-id="72abe-106">El depurador debe llamar a `Initialize` durante la creación de servicios de tiempo para inicializar la depuración.</span><span class="sxs-lookup"><span data-stu-id="72abe-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="72abe-107">Este método debe llamarse antes que cualquier otro método en `ICorDebug` se llama.</span><span class="sxs-lookup"><span data-stu-id="72abe-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72abe-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72abe-108">Requirements</span></span>  
 <span data-ttu-id="72abe-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72abe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72abe-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72abe-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72abe-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72abe-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72abe-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72abe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72abe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="72abe-113">See also</span></span>

- [<span data-ttu-id="72abe-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72abe-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
