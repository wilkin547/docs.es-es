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
ms.openlocfilehash: e5bab32f6d18c87b030f484a47bc3f1d525d2338
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729634"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="9f437-102">ICorDebugEval2::NewStringWithLength (Método)</span><span class="sxs-lookup"><span data-stu-id="9f437-102">ICorDebugEval2::NewStringWithLength Method</span></span>

<span data-ttu-id="9f437-103">Crea una cadena de la longitud especificada, con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="9f437-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f437-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f437-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f437-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f437-105">Parameters</span></span>  

 `string`  
 <span data-ttu-id="9f437-106">de Puntero al valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="9f437-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="9f437-107">de Longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="9f437-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f437-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f437-108">Remarks</span></span>  

 <span data-ttu-id="9f437-109">Si se espera que el carácter nulo final de la cadena esté en la cadena administrada, el llamador del `NewStringWithLength` método debe asegurarse de que la longitud de la cadena incluye el carácter nulo final.</span><span class="sxs-lookup"><span data-stu-id="9f437-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="9f437-110">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="9f437-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f437-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f437-111">Requirements</span></span>  

 <span data-ttu-id="9f437-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f437-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f437-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f437-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f437-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f437-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f437-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f437-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
