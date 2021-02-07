---
description: 'Más información acerca de: ICorDebugCode:: GetVersionNumber ((método)'
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
ms.openlocfilehash: 901342333bea3d455407602dde78bdccd0140d77
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764910"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="699ac-103">ICorDebugCode::GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="699ac-103">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="699ac-104">Obtiene el número basado en uno que identifica la versión del código que representa este "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="699ac-104">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="699ac-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="699ac-105">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="699ac-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="699ac-106">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="699ac-107">enuncia Puntero al número de versión del código.</span><span class="sxs-lookup"><span data-stu-id="699ac-107">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="699ac-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="699ac-108">Remarks</span></span>

 <span data-ttu-id="699ac-109">El número de versión se incrementa cada vez que se realiza una operación de edición y continuación (EnC) en el código.</span><span class="sxs-lookup"><span data-stu-id="699ac-109">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="699ac-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="699ac-110">Requirements</span></span>

 <span data-ttu-id="699ac-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="699ac-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="699ac-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="699ac-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="699ac-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="699ac-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="699ac-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="699ac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
