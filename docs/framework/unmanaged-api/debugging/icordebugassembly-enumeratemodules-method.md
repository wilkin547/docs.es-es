---
title: ICorDebugAssembly::EnumerateModules (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.EnumerateModules
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type:
- apiref
ms.openlocfilehash: 6d00d17a5876dd7454b9f89ffa916bc62efb3d0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734132"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="e2f5f-102">ICorDebugAssembly::EnumerateModules (Método)</span><span class="sxs-lookup"><span data-stu-id="e2f5f-102">ICorDebugAssembly::EnumerateModules Method</span></span>

<span data-ttu-id="e2f5f-103">Obtiene un enumerador para los módulos incluidos en `ICorDebugAssembly` .</span><span class="sxs-lookup"><span data-stu-id="e2f5f-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f5f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2f5f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2f5f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2f5f-105">Parameters</span></span>  

 `ppModules`  
 <span data-ttu-id="e2f5f-106">enuncia Puntero a la dirección de la interfaz ICorDebugModuleEnum (que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="e2f5f-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2f5f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2f5f-107">Requirements</span></span>  

 <span data-ttu-id="e2f5f-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2f5f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2f5f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2f5f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2f5f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2f5f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2f5f-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2f5f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
