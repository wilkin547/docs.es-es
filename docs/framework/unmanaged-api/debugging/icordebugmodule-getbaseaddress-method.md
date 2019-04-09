---
title: ICorDebugModule::GetBaseAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 763f2872099fac87138b7e1ab058c60475892b0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107424"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="73c58-102">ICorDebugModule::GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="73c58-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="73c58-103">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="73c58-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73c58-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73c58-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73c58-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="73c58-106">[out] Un `CORDB_ADDRESS` que especifica la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="73c58-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73c58-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73c58-107">Remarks</span></span>  
 <span data-ttu-id="73c58-108">Si el módulo es nativo de imagen (es decir, si el módulo se ha producido por el generador de imágenes nativas, NGen.exe), su dirección base será cero.</span><span class="sxs-lookup"><span data-stu-id="73c58-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73c58-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73c58-109">Requirements</span></span>  
 <span data-ttu-id="73c58-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73c58-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73c58-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73c58-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73c58-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73c58-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="73c58-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="73c58-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="73c58-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="73c58-114">See also</span></span>
