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
ms.openlocfilehash: aeecf19cb85ce5d7781c3dfedca079e97cab76ce
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895355"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="94ee8-102">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="94ee8-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="94ee8-103">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="94ee8-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ee8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94ee8-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="94ee8-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="94ee8-105">Remarks</span></span>  
 <span data-ttu-id="94ee8-106">El depurador debe `Initialize` llamar a en el momento de la creación para inicializar los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="94ee8-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="94ee8-107">Se debe llamar a este método antes de llamar a `ICorDebug` cualquier otro método en.</span><span class="sxs-lookup"><span data-stu-id="94ee8-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94ee8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94ee8-108">Requirements</span></span>  
 <span data-ttu-id="94ee8-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94ee8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94ee8-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94ee8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94ee8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94ee8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94ee8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94ee8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ee8-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="94ee8-113">See also</span></span>

- [<span data-ttu-id="94ee8-114">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94ee8-114">ICorDebug Interface</span></span>](icordebug-interface.md)
