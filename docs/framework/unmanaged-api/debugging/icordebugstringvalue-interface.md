---
title: ICorDebugStringValue (Interfaz)
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
ms.openlocfilehash: d1d3a5eb6e0b24b40a35c13a99465dd3c7032a91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138942"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="1d277-102">ICorDebugStringValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d277-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="1d277-103">Subclase de ICorDebugHeapValue que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="1d277-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d277-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1d277-104">Methods</span></span>  
  
|<span data-ttu-id="1d277-105">Método</span><span class="sxs-lookup"><span data-stu-id="1d277-105">Method</span></span>|<span data-ttu-id="1d277-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d277-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d277-107">GetLength (método)</span><span class="sxs-lookup"><span data-stu-id="1d277-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="1d277-108">Obtiene el número de caracteres de la cadena a la que hace referencia este `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="1d277-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="1d277-109">GetString (método)</span><span class="sxs-lookup"><span data-stu-id="1d277-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="1d277-110">Obtiene la cadena a la que hace referencia este `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="1d277-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d277-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1d277-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d277-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1d277-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d277-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d277-113">Requirements</span></span>  
 <span data-ttu-id="1d277-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d277-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d277-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d277-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d277-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d277-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d277-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d277-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d277-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d277-118">See also</span></span>

- [<span data-ttu-id="1d277-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1d277-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
