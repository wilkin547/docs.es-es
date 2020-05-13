---
title: ICorDebugModule::GetAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
ms.openlocfilehash: 86e2b28448caf2a872e44490e8ee4763b056ed44
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206968"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="85d71-102">ICorDebugModule::GetAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="85d71-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="85d71-103">Obtiene el ensamblado contenedor de este módulo.</span><span class="sxs-lookup"><span data-stu-id="85d71-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85d71-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85d71-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85d71-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="85d71-106">enuncia Un puntero a un objeto ICorDebugAssembly que representa el ensamblado que contiene este módulo.</span><span class="sxs-lookup"><span data-stu-id="85d71-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85d71-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85d71-107">Requirements</span></span>  
 <span data-ttu-id="85d71-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85d71-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85d71-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85d71-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85d71-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85d71-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85d71-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85d71-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
