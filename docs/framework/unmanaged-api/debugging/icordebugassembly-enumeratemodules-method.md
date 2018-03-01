---
title: "ICorDebugAssembly::EnumerateModules (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5bc6aced78d1d7ffc6521bca52bed1b2e232bbe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="b3c5b-102">ICorDebugAssembly::EnumerateModules (Método)</span><span class="sxs-lookup"><span data-stu-id="b3c5b-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="b3c5b-103">Obtiene un enumerador para los módulos incluidos en el `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="b3c5b-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3c5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3c5b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3c5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3c5b-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="b3c5b-106">[out] Un puntero a la dirección de la interfaz de ICorDebugModuleEnum que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="b3c5b-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3c5b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3c5b-107">Requirements</span></span>  
 <span data-ttu-id="b3c5b-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3c5b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c5b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3c5b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3c5b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3c5b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3c5b-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3c5b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
