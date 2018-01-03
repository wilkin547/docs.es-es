---
title: "ICorDebugClass::GetToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass.GetToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 408575c53feb81a2b273bd1064e2d3eaa37c4fb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="48d59-102">ICorDebugClass::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="48d59-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="48d59-103">Obtiene el `TypeDef` símbolo (token) de metadatos que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="48d59-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d59-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48d59-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48d59-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48d59-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="48d59-106">[out] Un puntero a un `mdTypeDef` símbolo (token) que hace referencia a la definición de esta clase.</span><span class="sxs-lookup"><span data-stu-id="48d59-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d59-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48d59-107">Requirements</span></span>  
 <span data-ttu-id="48d59-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d59-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d59-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48d59-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48d59-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48d59-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48d59-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d59-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d59-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="48d59-112">See Also</span></span>  
 [<span data-ttu-id="48d59-113">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="48d59-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
