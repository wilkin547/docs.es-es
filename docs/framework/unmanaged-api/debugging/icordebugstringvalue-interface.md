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
ms.openlocfilehash: cd6c5726b9a938d04cf4eb018ec9851c81d9c745
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697069"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="a62e9-102">Interfaz ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="a62e9-102">ICorDebugStringValue Interface</span></span>

<span data-ttu-id="a62e9-103">Subclase de ICorDebugHeapValue que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="a62e9-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a62e9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a62e9-104">Methods</span></span>  
  
|<span data-ttu-id="a62e9-105">Método</span><span class="sxs-lookup"><span data-stu-id="a62e9-105">Method</span></span>|<span data-ttu-id="a62e9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a62e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a62e9-107">Método GetLength</span><span class="sxs-lookup"><span data-stu-id="a62e9-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="a62e9-108">Obtiene el número de caracteres de la cadena a la que hace referencia este `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="a62e9-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="a62e9-109">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="a62e9-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="a62e9-110">Obtiene la cadena a la que hace referencia este `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="a62e9-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a62e9-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a62e9-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a62e9-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a62e9-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a62e9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a62e9-113">Requirements</span></span>  

 <span data-ttu-id="a62e9-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a62e9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a62e9-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a62e9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a62e9-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a62e9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a62e9-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a62e9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62e9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a62e9-118">See also</span></span>

- [<span data-ttu-id="a62e9-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a62e9-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
