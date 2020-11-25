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
ms.openlocfilehash: c2d29a0cc344539bf515793c071fe839aa441ebc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729738"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="14fd3-102">ICorDebugEval::NewString (Método)</span><span class="sxs-lookup"><span data-stu-id="14fd3-102">ICorDebugEval::NewString Method</span></span>

<span data-ttu-id="14fd3-103">Asigna una nueva instancia de cadena con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="14fd3-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14fd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14fd3-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14fd3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14fd3-105">Parameters</span></span>  

 `string`  
 <span data-ttu-id="14fd3-106">de Puntero al contenido de la cadena.</span><span class="sxs-lookup"><span data-stu-id="14fd3-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14fd3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14fd3-107">Remarks</span></span>  

 <span data-ttu-id="14fd3-108">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="14fd3-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14fd3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14fd3-109">Requirements</span></span>  

 <span data-ttu-id="14fd3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14fd3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14fd3-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14fd3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14fd3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14fd3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14fd3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14fd3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
