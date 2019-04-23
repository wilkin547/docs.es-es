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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6709b14ce8e7bc131f9feb7a277fb41851ee4352
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173997"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="ce106-102">Interfaz ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="ce106-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="ce106-103">Una subclase del ICorDebugHeapValue que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="ce106-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce106-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ce106-104">Methods</span></span>  
  
|<span data-ttu-id="ce106-105">Método</span><span class="sxs-lookup"><span data-stu-id="ce106-105">Method</span></span>|<span data-ttu-id="ce106-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce106-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce106-107">GetLength (método)</span><span class="sxs-lookup"><span data-stu-id="ce106-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="ce106-108">Obtiene el número de caracteres de la cadena que hace referencia esta `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="ce106-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="ce106-109">GetString (método)</span><span class="sxs-lookup"><span data-stu-id="ce106-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="ce106-110">Obtiene la cadena que hace referencia esta `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="ce106-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce106-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce106-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce106-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ce106-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce106-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce106-113">Requirements</span></span>  
 <span data-ttu-id="ce106-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce106-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce106-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce106-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce106-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce106-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce106-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce106-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce106-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce106-118">See also</span></span>

- [<span data-ttu-id="ce106-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ce106-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
