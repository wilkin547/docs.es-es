---
description: 'Más información sobre: interfaz ICorDebugStringValue'
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
ms.openlocfilehash: b4e762d8c0a62c1b76b59364e9d29c4b8d2386fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717336"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="cb4f2-103">Interfaz ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="cb4f2-103">ICorDebugStringValue Interface</span></span>

<span data-ttu-id="cb4f2-104">Subclase de ICorDebugHeapValue que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="cb4f2-104">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb4f2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cb4f2-105">Methods</span></span>  
  
|<span data-ttu-id="cb4f2-106">Método</span><span class="sxs-lookup"><span data-stu-id="cb4f2-106">Method</span></span>|<span data-ttu-id="cb4f2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb4f2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb4f2-108">Método GetLength</span><span class="sxs-lookup"><span data-stu-id="cb4f2-108">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="cb4f2-109">Obtiene el número de caracteres de la cadena a la que hace referencia este `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="cb4f2-109">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="cb4f2-110">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="cb4f2-110">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="cb4f2-111">Obtiene la cadena a la que hace referencia este `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="cb4f2-111">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb4f2-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb4f2-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb4f2-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cb4f2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb4f2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb4f2-114">Requirements</span></span>  

 <span data-ttu-id="cb4f2-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb4f2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb4f2-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb4f2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb4f2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb4f2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb4f2-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb4f2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4f2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb4f2-119">See also</span></span>

- [<span data-ttu-id="cb4f2-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cb4f2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
