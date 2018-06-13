---
title: ICorDebugStringValue Interfaz1
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
ms.openlocfilehash: 2814f6164f383c36bb5b8e20ce8996b30eef0f1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421705"
---
# <a name="icordebugstringvalue-interface1"></a><span data-ttu-id="dc072-102">ICorDebugStringValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="dc072-102">ICorDebugStringValue Interface1</span></span>
<span data-ttu-id="dc072-103">Una subclase de ICorDebugHeapValue que se aplica a valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="dc072-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc072-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dc072-104">Methods</span></span>  
  
|<span data-ttu-id="dc072-105">Método</span><span class="sxs-lookup"><span data-stu-id="dc072-105">Method</span></span>|<span data-ttu-id="dc072-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc072-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc072-107">GetLength (método)</span><span class="sxs-lookup"><span data-stu-id="dc072-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="dc072-108">Obtiene el número de caracteres de la cadena que hace referencia esta `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="dc072-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="dc072-109">GetString (método)</span><span class="sxs-lookup"><span data-stu-id="dc072-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="dc072-110">Obtiene la cadena que hace referencia esta `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="dc072-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc072-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc072-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc072-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="dc072-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc072-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc072-113">Requirements</span></span>  
 <span data-ttu-id="dc072-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc072-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc072-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc072-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc072-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc072-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc072-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc072-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc072-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc072-118">See Also</span></span>  
 [<span data-ttu-id="dc072-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dc072-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
