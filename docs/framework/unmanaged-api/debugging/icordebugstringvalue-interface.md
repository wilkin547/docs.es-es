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
ms.openlocfilehash: 6c232163f7c18086804eca7990a0890a507ef00b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791680"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="3613a-102">Interfaz ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="3613a-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="3613a-103">Subclase de ICorDebugHeapValue que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="3613a-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3613a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3613a-104">Methods</span></span>  
  
|<span data-ttu-id="3613a-105">Método</span><span class="sxs-lookup"><span data-stu-id="3613a-105">Method</span></span>|<span data-ttu-id="3613a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3613a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3613a-107">GetLength (método)</span><span class="sxs-lookup"><span data-stu-id="3613a-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="3613a-108">Obtiene el número de caracteres de la cadena a la que hace referencia este `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="3613a-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="3613a-109">GetString (método)</span><span class="sxs-lookup"><span data-stu-id="3613a-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="3613a-110">Obtiene la cadena a la que hace referencia este `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="3613a-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3613a-111">Notas</span><span class="sxs-lookup"><span data-stu-id="3613a-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3613a-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3613a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3613a-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3613a-113">Requirements</span></span>  
 <span data-ttu-id="3613a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3613a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3613a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3613a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3613a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3613a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3613a-117">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3613a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3613a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3613a-118">See also</span></span>

- [<span data-ttu-id="3613a-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3613a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
