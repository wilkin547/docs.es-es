---
description: 'Más información acerca de: ICorDebug:: Initialize (método)'
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
ms.openlocfilehash: 6b6ddd8c1c21470477420909bcf75906b5731ee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791600"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="55d70-103">ICorDebug::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="55d70-103">ICorDebug::Initialize Method</span></span>

<span data-ttu-id="55d70-104">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="55d70-104">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55d70-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55d70-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="55d70-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55d70-106">Remarks</span></span>  

 <span data-ttu-id="55d70-107">El depurador debe llamar a `Initialize` en el momento de la creación para inicializar los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="55d70-107">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="55d70-108">Se debe llamar a este método antes de llamar a cualquier otro método en `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="55d70-108">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55d70-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55d70-109">Requirements</span></span>  

 <span data-ttu-id="55d70-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55d70-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55d70-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55d70-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55d70-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55d70-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55d70-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55d70-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d70-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="55d70-114">See also</span></span>

- [<span data-ttu-id="55d70-115">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55d70-115">ICorDebug Interface</span></span>](icordebug-interface.md)
