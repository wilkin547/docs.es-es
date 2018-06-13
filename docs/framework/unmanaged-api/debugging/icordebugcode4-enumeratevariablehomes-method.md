---
title: ICorDebugCode4::EnumerateVariableHomes (método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e1c8157d5a5e4a1bd52f187de7c1d3bfcc4e66d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410925"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="a5590-102">ICorDebugCode4::EnumerateVariableHomes (método)</span><span class="sxs-lookup"><span data-stu-id="a5590-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="a5590-103">Obtiene un enumerador para las variables locales y argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="a5590-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5590-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5590-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5590-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5590-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a5590-106">Un puntero a la dirección de un [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) objeto de interfaz que es un enumerador para las variables locales y argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="a5590-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5590-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5590-107">Remarks</span></span>  
 <span data-ttu-id="a5590-108">El [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) objeto de interfaz es un enumerador estándar que se deriva de la interfaz de "ICorDebugEnum" que permite enumerar [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="a5590-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="a5590-109">La colección puede incluir varios [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) de objetos para el mismo índice de ranura o argumento si disponen de casas diferentes en distintos puntos de la función.</span><span class="sxs-lookup"><span data-stu-id="a5590-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5590-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5590-110">Requirements</span></span>  
 <span data-ttu-id="a5590-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5590-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5590-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5590-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5590-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5590-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5590-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5590-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5590-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5590-115">See Also</span></span>  
 [<span data-ttu-id="a5590-116">ICorDebugCode4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5590-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 [<span data-ttu-id="a5590-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a5590-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
