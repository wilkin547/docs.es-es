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
ms.openlocfilehash: 9ed6344f9a37d246a551699c94046b8c2b473fd8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762695"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="cafd8-102">ICorDebugModule::GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="cafd8-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="cafd8-103">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="cafd8-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cafd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cafd8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cafd8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cafd8-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="cafd8-106">[out] Un `CORDB_ADDRESS` que especifica la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="cafd8-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cafd8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cafd8-107">Remarks</span></span>  
 <span data-ttu-id="cafd8-108">Si el módulo es nativo de imagen (es decir, si el módulo se ha producido por el generador de imágenes nativas, NGen.exe), su dirección base será cero.</span><span class="sxs-lookup"><span data-stu-id="cafd8-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cafd8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cafd8-109">Requirements</span></span>  
 <span data-ttu-id="cafd8-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cafd8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cafd8-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cafd8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cafd8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cafd8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cafd8-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cafd8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafd8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cafd8-114">See also</span></span>
