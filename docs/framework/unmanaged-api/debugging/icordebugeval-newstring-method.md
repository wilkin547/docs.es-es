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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db609bdee7975b6c067271f99529e2cf2240f720
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480187"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="7647c-102">ICorDebugEval::NewString (Método)</span><span class="sxs-lookup"><span data-stu-id="7647c-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="7647c-103">Asigna una nueva instancia de la cadena con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="7647c-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7647c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7647c-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7647c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7647c-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="7647c-106">[in] Puntero al contenido de la cadena.</span><span class="sxs-lookup"><span data-stu-id="7647c-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7647c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7647c-107">Remarks</span></span>  
 <span data-ttu-id="7647c-108">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="7647c-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7647c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7647c-109">Requirements</span></span>  
 <span data-ttu-id="7647c-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7647c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7647c-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7647c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7647c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7647c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7647c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7647c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
