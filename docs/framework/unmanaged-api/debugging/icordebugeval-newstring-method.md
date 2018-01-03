---
title: "ICorDebugEval::NewString (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.NewString
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cc45d766801391fcd157c39357058be17759f8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="3d9a8-102">ICorDebugEval::NewString (Método)</span><span class="sxs-lookup"><span data-stu-id="3d9a8-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="3d9a8-103">Asigna una nueva instancia de cadena con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="3d9a8-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d9a8-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d9a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d9a8-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="3d9a8-106">[in] Puntero al contenido de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3d9a8-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d9a8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d9a8-107">Remarks</span></span>  
 <span data-ttu-id="3d9a8-108">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="3d9a8-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d9a8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d9a8-109">Requirements</span></span>  
 <span data-ttu-id="3d9a8-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d9a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9a8-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d9a8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d9a8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d9a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d9a8-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d9a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
