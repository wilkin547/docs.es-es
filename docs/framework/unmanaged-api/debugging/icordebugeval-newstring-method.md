---
title: ICorDebugEval::NewString (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: 8a5d421bf0eb8ec5a34fe21d6efc79bbe56c294c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137642"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="bfbc7-102">ICorDebugEval::NewString (Método)</span><span class="sxs-lookup"><span data-stu-id="bfbc7-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="bfbc7-103">Asigna una nueva instancia de cadena con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="bfbc7-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfbc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfbc7-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfbc7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfbc7-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="bfbc7-106">de Puntero al contenido de la cadena.</span><span class="sxs-lookup"><span data-stu-id="bfbc7-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfbc7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfbc7-107">Remarks</span></span>  
 <span data-ttu-id="bfbc7-108">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="bfbc7-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfbc7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfbc7-109">Requirements</span></span>  
 <span data-ttu-id="bfbc7-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfbc7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfbc7-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfbc7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfbc7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfbc7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfbc7-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfbc7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
