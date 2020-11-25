---
title: ICorDebugILFrame::EnumerateLocalVariables (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 968ceec53aade3d04c500c8247d397ffb71382c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703211"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="fa98b-102">ICorDebugILFrame::EnumerateLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="fa98b-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>

<span data-ttu-id="fa98b-103">Obtiene un enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="fa98b-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa98b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa98b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa98b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa98b-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="fa98b-106">[out] Puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador de las variables locales en este marco.</span><span class="sxs-lookup"><span data-stu-id="fa98b-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa98b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa98b-107">Remarks</span></span>  

 <span data-ttu-id="fa98b-108">`EnumerateLocalVariables` Obtiene un enumerador que puede enumerar las variables locales disponibles en el marco de llamada representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="fa98b-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="fa98b-109">La lista puede no incluir todas las variables locales de la función en ejecución, porque algunas de ellas pueden no estar activas.</span><span class="sxs-lookup"><span data-stu-id="fa98b-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa98b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa98b-110">Requirements</span></span>  

 <span data-ttu-id="fa98b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa98b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa98b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa98b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa98b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa98b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa98b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa98b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
