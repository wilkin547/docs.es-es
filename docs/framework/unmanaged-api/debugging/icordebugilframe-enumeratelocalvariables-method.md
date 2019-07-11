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
ms.openlocfilehash: c18f2fce23e979f27d9116e74b6c6b007cd33bf0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752888"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="bb7dd-102">ICorDebugILFrame::EnumerateLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="bb7dd-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="bb7dd-103">Obtiene un enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="bb7dd-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb7dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb7dd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb7dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb7dd-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="bb7dd-106">[out] Un puntero a la dirección de un objeto ICorDebugValueEnum que es el enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="bb7dd-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb7dd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb7dd-107">Remarks</span></span>  
 <span data-ttu-id="bb7dd-108">`EnumerateLocalVariables` Obtiene un enumerador que puede enumerar las variables locales disponibles en el marco de llamada representado por este objeto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="bb7dd-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="bb7dd-109">La lista puede no incluir todas las variables locales en la función de la ejecución, porque algunos de ellos no pueden estar activo.</span><span class="sxs-lookup"><span data-stu-id="bb7dd-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb7dd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb7dd-110">Requirements</span></span>  
 <span data-ttu-id="bb7dd-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb7dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb7dd-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb7dd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb7dd-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb7dd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb7dd-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb7dd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
