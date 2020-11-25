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
ms.openlocfilehash: 5cdd89ebdbb5abb9b001c1489a54bfb867808c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723433"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="cdc55-102">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="cdc55-102">ICorDebug::Initialize Method</span></span>

<span data-ttu-id="cdc55-103">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="cdc55-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdc55-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cdc55-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cdc55-105">Remarks</span></span>  

 <span data-ttu-id="cdc55-106">El depurador debe llamar a `Initialize` en el momento de la creación para inicializar los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="cdc55-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="cdc55-107">Se debe llamar a este método antes de llamar a cualquier otro método en `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="cdc55-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdc55-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cdc55-108">Requirements</span></span>  

 <span data-ttu-id="cdc55-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdc55-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdc55-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdc55-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdc55-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdc55-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdc55-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdc55-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc55-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cdc55-113">See also</span></span>

- [<span data-ttu-id="cdc55-114">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cdc55-114">ICorDebug Interface</span></span>](icordebug-interface.md)
