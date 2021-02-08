---
description: 'Más información acerca de: ICorDebugModule:: GetBaseAddress ((método)'
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
ms.openlocfilehash: bdfa4aeac3a9c06f666d56f1ee08ec503626ce7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790820"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="823da-103">ICorDebugModule::GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="823da-103">ICorDebugModule::GetBaseAddress Method</span></span>

<span data-ttu-id="823da-104">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="823da-104">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="823da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="823da-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="823da-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="823da-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="823da-107">enuncia `CORDB_ADDRESS` Que especifica la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="823da-107">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="823da-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="823da-108">Remarks</span></span>  

 <span data-ttu-id="823da-109">Si el módulo es una imagen nativa (es decir, si el generador de imágenes nativas generó el módulo, NGen.exe), su dirección base será cero.</span><span class="sxs-lookup"><span data-stu-id="823da-109">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="823da-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="823da-110">Requirements</span></span>  

 <span data-ttu-id="823da-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="823da-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="823da-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="823da-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="823da-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="823da-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="823da-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="823da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="823da-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="823da-115">See also</span></span>
