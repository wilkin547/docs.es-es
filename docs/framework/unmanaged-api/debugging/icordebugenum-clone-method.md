---
title: ICorDebugEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d1226f64df379b5c40304221e9e66eebcdb17b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989136"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="7cd38-102">ICorDebugEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="7cd38-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="7cd38-103">Crea una copia de este objeto ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="7cd38-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cd38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cd38-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cd38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7cd38-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7cd38-106">[out] Un puntero a la dirección de un `ICorDebugEnum` objeto que es una copia de este `ICorDebugEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="7cd38-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cd38-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cd38-107">Requirements</span></span>  
 <span data-ttu-id="7cd38-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cd38-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cd38-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cd38-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cd38-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cd38-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cd38-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cd38-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
