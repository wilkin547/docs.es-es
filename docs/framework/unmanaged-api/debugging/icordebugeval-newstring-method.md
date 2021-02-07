---
description: 'Más información acerca de: ICorDebugEval:: Newstring ((método)'
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
ms.openlocfilehash: 21eb49900d84cb1ad1f68a701998a4a778c3ef17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693848"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="9a1fe-103">ICorDebugEval::NewString (Método)</span><span class="sxs-lookup"><span data-stu-id="9a1fe-103">ICorDebugEval::NewString Method</span></span>

<span data-ttu-id="9a1fe-104">Asigna una nueva instancia de cadena con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="9a1fe-104">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a1fe-105">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a1fe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a1fe-106">Parameters</span></span>  

 `string`  
 <span data-ttu-id="9a1fe-107">de Puntero al contenido de la cadena.</span><span class="sxs-lookup"><span data-stu-id="9a1fe-107">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a1fe-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9a1fe-108">Remarks</span></span>  

 <span data-ttu-id="9a1fe-109">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="9a1fe-109">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a1fe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a1fe-110">Requirements</span></span>  

 <span data-ttu-id="9a1fe-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a1fe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a1fe-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a1fe-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a1fe-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a1fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a1fe-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a1fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
