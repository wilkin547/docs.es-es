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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cc9601105d05740e6db0a41bae521bd9a276d74
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471321"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="23e68-102">ICorDebugILFrame::EnumerateLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="23e68-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="23e68-103">Obtiene un enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="23e68-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23e68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23e68-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23e68-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23e68-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="23e68-106">[out] Un puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="23e68-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23e68-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23e68-107">Remarks</span></span>  
 <span data-ttu-id="23e68-108">`EnumerateLocalVariables` Obtiene un enumerador que puede enumerar las variables locales disponibles en el marco de llamada representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="23e68-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="23e68-109">La lista puede no incluir todas las variables locales en la función de la ejecución, porque algunos de ellos no pueden estar activo.</span><span class="sxs-lookup"><span data-stu-id="23e68-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23e68-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23e68-110">Requirements</span></span>  
 <span data-ttu-id="23e68-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23e68-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23e68-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23e68-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23e68-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23e68-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23e68-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23e68-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
