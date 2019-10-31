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
ms.openlocfilehash: 646c20ca1b78ff0ce513b8a3c9b578c3b1b9a696
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125597"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="bb6b2-102">ICorDebugCode::GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="bb6b2-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="bb6b2-103">Obtiene el número basado en uno que identifica la versión del código que representa este "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="bb6b2-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb6b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb6b2-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="bb6b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb6b2-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="bb6b2-106">enuncia Puntero al número de versión del código.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb6b2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb6b2-107">Remarks</span></span>

 <span data-ttu-id="bb6b2-108">El número de versión se incrementa cada vez que se realiza una operación de edición y continuación (EnC) en el código.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb6b2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb6b2-109">Requirements</span></span>

 <span data-ttu-id="bb6b2-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb6b2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb6b2-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb6b2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb6b2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb6b2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb6b2-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb6b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
