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
ms.openlocfilehash: 4b6fd6e8043f1c62da8994b43a9b9af45fb2e3c0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700822"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="1c194-102">ICorDebugCode::GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="1c194-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="1c194-103">Obtiene el número basado en uno que identifica la versión del código que representa este "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="1c194-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="1c194-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c194-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="1c194-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c194-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="1c194-106">enuncia Puntero al número de versión del código.</span><span class="sxs-lookup"><span data-stu-id="1c194-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c194-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c194-107">Remarks</span></span>

 <span data-ttu-id="1c194-108">El número de versión se incrementa cada vez que se realiza una operación de edición y continuación (EnC) en el código.</span><span class="sxs-lookup"><span data-stu-id="1c194-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c194-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c194-109">Requirements</span></span>

 <span data-ttu-id="1c194-110">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c194-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c194-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1c194-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c194-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c194-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c194-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c194-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
