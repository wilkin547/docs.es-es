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
ms.openlocfilehash: 9270afa1d8c8ddd74cfe6dd05e39c1480f5767e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206943"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="4bfc3-102">ICorDebugModule::GetBaseAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="4bfc3-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="4bfc3-103">Obtiene la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bfc3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bfc3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4bfc3-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="4bfc3-106">enuncia `CORDB_ADDRESS`Que especifica la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bfc3-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4bfc3-107">Remarks</span></span>  
 <span data-ttu-id="4bfc3-108">Si el módulo es una imagen nativa (es decir, si el generador de imágenes nativas, NGen. exe) ha generado el módulo, su dirección base será cero.</span><span class="sxs-lookup"><span data-stu-id="4bfc3-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bfc3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bfc3-109">Requirements</span></span>  
 <span data-ttu-id="4bfc3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bfc3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bfc3-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bfc3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bfc3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bfc3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bfc3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bfc3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfc3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4bfc3-114">See also</span></span>
