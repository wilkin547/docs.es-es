---
title: "ICorDebugClass::GetModule (Método)"
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
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77997d083a184ff20df749933f21eefafc2b9e3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="a9f60-102">ICorDebugClass::GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="a9f60-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="a9f60-103">Obtiene el módulo que define esta clase.</span><span class="sxs-lookup"><span data-stu-id="a9f60-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f60-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9f60-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9f60-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9f60-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="a9f60-106">[out] Un puntero a la dirección de un objeto ICorDebugModule que representa el módulo en el que se define esta clase.</span><span class="sxs-lookup"><span data-stu-id="a9f60-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9f60-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9f60-107">Requirements</span></span>  
 <span data-ttu-id="a9f60-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9f60-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9f60-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9f60-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9f60-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9f60-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9f60-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9f60-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
