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
ms.openlocfilehash: c071a7ddb7d8d3f0e6487ab85284c45f9a7f0372
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178839"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="3a933-102">ICorDebugILFrame::EnumerateLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="3a933-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="3a933-103">Obtiene un enumerador para las variables locales en este marco.</span><span class="sxs-lookup"><span data-stu-id="3a933-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a933-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a933-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a933-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a933-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="3a933-106">[out] Puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador de las variables locales en este marco.</span><span class="sxs-lookup"><span data-stu-id="3a933-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a933-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a933-107">Remarks</span></span>  
 <span data-ttu-id="3a933-108">`EnumerateLocalVariables`obtiene un enumerador que puede enumerar las variables locales disponibles en el marco de llamada representado por este ICorDebugILFrame objeto.</span><span class="sxs-lookup"><span data-stu-id="3a933-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="3a933-109">Es posible que la lista no incluya todas las variables locales en la función en ejecución, ya que es posible que algunas de ellas no estén activas.</span><span class="sxs-lookup"><span data-stu-id="3a933-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a933-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a933-110">Requirements</span></span>  
 <span data-ttu-id="3a933-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a933-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a933-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a933-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a933-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a933-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a933-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a933-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
