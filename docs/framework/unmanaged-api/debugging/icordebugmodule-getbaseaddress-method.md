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
ms.openlocfilehash: 4562318c87b79fba5f3d99860ee438c0144e9aae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710251"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="3212b-102">ICorDebugModule::GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="3212b-102">ICorDebugModule::GetBaseAddress Method</span></span>

<span data-ttu-id="3212b-103">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="3212b-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3212b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3212b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3212b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3212b-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="3212b-106">enuncia `CORDB_ADDRESS` Que especifica la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="3212b-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3212b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3212b-107">Remarks</span></span>  

 <span data-ttu-id="3212b-108">Si el módulo es una imagen nativa (es decir, si el generador de imágenes nativas generó el módulo, NGen.exe), su dirección base será cero.</span><span class="sxs-lookup"><span data-stu-id="3212b-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3212b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3212b-109">Requirements</span></span>  

 <span data-ttu-id="3212b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3212b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3212b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3212b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3212b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3212b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3212b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3212b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3212b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3212b-114">See also</span></span>
