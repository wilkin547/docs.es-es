---
title: ICorDebugEval2::NewStringWithLength (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
ms.openlocfilehash: 3836b6c08098d38516c8a25260fb28998a2317fe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084782"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="a445f-102">ICorDebugEval2::NewStringWithLength (Método)</span><span class="sxs-lookup"><span data-stu-id="a445f-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="a445f-103">Crea una cadena de la longitud especificada, con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="a445f-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a445f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a445f-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a445f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a445f-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="a445f-106">de Puntero al valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="a445f-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="a445f-107">de Longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="a445f-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a445f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a445f-108">Remarks</span></span>  
 <span data-ttu-id="a445f-109">Si se espera que el carácter nulo final de la cadena esté en la cadena administrada, el llamador del método `NewStringWithLength` debe asegurarse de que la longitud de la cadena incluye el carácter nulo final.</span><span class="sxs-lookup"><span data-stu-id="a445f-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="a445f-110">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="a445f-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a445f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a445f-111">Requirements</span></span>  
 <span data-ttu-id="a445f-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a445f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a445f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a445f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a445f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a445f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a445f-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a445f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
