---
title: ICorDebugAssembly::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
ms.openlocfilehash: e8662535fb6f1aa812130d96e67678baa3c41a52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734041"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="3f91f-102">ICorDebugAssembly::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="3f91f-102">ICorDebugAssembly::GetProcess Method</span></span>

<span data-ttu-id="3f91f-103">Obtiene un puntero de interfaz al proceso en el que se está ejecutando esta instancia de ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="3f91f-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f91f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f91f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f91f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f91f-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="3f91f-106">enuncia Puntero a una interfaz ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="3f91f-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f91f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f91f-107">Requirements</span></span>  

 <span data-ttu-id="3f91f-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f91f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f91f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f91f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f91f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f91f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f91f-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f91f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
