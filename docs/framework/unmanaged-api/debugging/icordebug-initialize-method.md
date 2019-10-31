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
ms.openlocfilehash: a5cda98cac0bc3fc6fb101fd0404b062224cb578
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134079"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="feefd-102">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="feefd-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="feefd-103">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="feefd-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feefd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="feefd-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="feefd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="feefd-105">Remarks</span></span>  
 <span data-ttu-id="feefd-106">El depurador debe llamar a `Initialize` en el momento de la creación para inicializar los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="feefd-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="feefd-107">Se debe llamar a este método antes de llamar a cualquier otro método en `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="feefd-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feefd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="feefd-108">Requirements</span></span>  
 <span data-ttu-id="feefd-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feefd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feefd-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="feefd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="feefd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feefd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feefd-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feefd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feefd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="feefd-113">See also</span></span>

- [<span data-ttu-id="feefd-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="feefd-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
