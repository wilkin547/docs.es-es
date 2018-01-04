---
title: "ICorDebugILFrame::EnumerateLocalVariables (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateLocalVariables
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a1b53dbefefcea6003ec4a61c8169ed96bac701
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="d95c2-102">ICorDebugILFrame::EnumerateLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="d95c2-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="d95c2-103">Obtiene un enumerador para las variables locales en este marco.</span><span class="sxs-lookup"><span data-stu-id="d95c2-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d95c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d95c2-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d95c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d95c2-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="d95c2-106">[out] Un puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="d95c2-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d95c2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d95c2-107">Remarks</span></span>  
 <span data-ttu-id="d95c2-108">`EnumerateLocalVariables`Obtiene un enumerador que puede enumerar las variables locales disponibles en el marco de llamadas representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="d95c2-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="d95c2-109">La lista puede no incluir todas las variables locales en la función en ejecución, porque algunos de ellos pueden no estar activas.</span><span class="sxs-lookup"><span data-stu-id="d95c2-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d95c2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d95c2-110">Requirements</span></span>  
 <span data-ttu-id="d95c2-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d95c2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d95c2-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d95c2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d95c2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d95c2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d95c2-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d95c2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
