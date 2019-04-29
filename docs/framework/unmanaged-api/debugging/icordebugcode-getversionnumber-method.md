---
title: ICorDebugCode::GetVersionNumber (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003b29501e8f22ed9010a9f16a4f7ee67bce03a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750142"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="89028-102">ICorDebugCode::GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="89028-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="89028-103">Obtiene el número basado en uno que identifica la versión del código que representa esta "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="89028-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89028-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89028-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89028-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89028-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="89028-106">[out] Un puntero al número de versión del código.</span><span class="sxs-lookup"><span data-stu-id="89028-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89028-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89028-107">Remarks</span></span>  
 <span data-ttu-id="89028-108">El número de versión se incrementa cada vez que un editar y continuar (EnC) se realiza en el código.</span><span class="sxs-lookup"><span data-stu-id="89028-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89028-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89028-109">Requirements</span></span>  
 <span data-ttu-id="89028-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89028-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89028-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89028-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89028-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89028-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89028-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89028-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89028-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="89028-114">See also</span></span>
