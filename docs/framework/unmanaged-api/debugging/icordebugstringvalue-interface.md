---
title: Interfaz ICorDebugStringValue
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
ms.openlocfilehash: 5537a48fd085ce98de855fa1ec0913e2637e58e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376193"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="ae72e-102">Interfaz ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="ae72e-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="ae72e-103">Subclase de ICorDebugHeapValue que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="ae72e-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae72e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ae72e-104">Methods</span></span>  
  
|<span data-ttu-id="ae72e-105">Método</span><span class="sxs-lookup"><span data-stu-id="ae72e-105">Method</span></span>|<span data-ttu-id="ae72e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae72e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae72e-107">Método GetLength</span><span class="sxs-lookup"><span data-stu-id="ae72e-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="ae72e-108">Obtiene el número de caracteres de la cadena a la que hace referencia este `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="ae72e-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="ae72e-109">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="ae72e-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="ae72e-110">Obtiene la cadena a la que hace referencia este `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="ae72e-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae72e-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ae72e-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae72e-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ae72e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae72e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae72e-113">Requirements</span></span>  
 <span data-ttu-id="ae72e-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae72e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae72e-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae72e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae72e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae72e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae72e-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae72e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae72e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae72e-118">See also</span></span>

- [<span data-ttu-id="ae72e-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ae72e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
