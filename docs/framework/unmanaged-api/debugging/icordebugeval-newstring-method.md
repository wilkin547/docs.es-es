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
ms.openlocfilehash: b263fed7db5cb2ef687da45f8cbc99a02e1e3ea2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976140"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="9b34c-102">ICorDebugEval::NewString (Método)</span><span class="sxs-lookup"><span data-stu-id="9b34c-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="9b34c-103">Asigna una nueva instancia de cadena con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="9b34c-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b34c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b34c-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b34c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b34c-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="9b34c-106">de Puntero al contenido de la cadena.</span><span class="sxs-lookup"><span data-stu-id="9b34c-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b34c-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9b34c-107">Remarks</span></span>  
 <span data-ttu-id="9b34c-108">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="9b34c-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b34c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b34c-109">Requirements</span></span>  
 <span data-ttu-id="9b34c-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b34c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b34c-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b34c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b34c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b34c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b34c-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b34c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
