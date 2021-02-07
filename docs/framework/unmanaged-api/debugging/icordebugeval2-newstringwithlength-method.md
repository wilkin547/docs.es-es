---
description: 'Más información sobre: ICorDebugEval2:: Newstringwithlength ((método)'
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
ms.openlocfilehash: 23864dabefcb4fc12f73c66bc2d19a6cca1aacf0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693530"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="d1f72-103">ICorDebugEval2::NewStringWithLength (Método)</span><span class="sxs-lookup"><span data-stu-id="d1f72-103">ICorDebugEval2::NewStringWithLength Method</span></span>

<span data-ttu-id="d1f72-104">Crea una cadena de la longitud especificada, con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="d1f72-104">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f72-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1f72-105">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1f72-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1f72-106">Parameters</span></span>  

 `string`  
 <span data-ttu-id="d1f72-107">de Puntero al valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="d1f72-107">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="d1f72-108">de Longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="d1f72-108">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1f72-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d1f72-109">Remarks</span></span>  

 <span data-ttu-id="d1f72-110">Si se espera que el carácter nulo final de la cadena esté en la cadena administrada, el llamador del `NewStringWithLength` método debe asegurarse de que la longitud de la cadena incluye el carácter nulo final.</span><span class="sxs-lookup"><span data-stu-id="d1f72-110">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="d1f72-111">La cadena siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d1f72-111">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f72-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1f72-112">Requirements</span></span>  

 <span data-ttu-id="d1f72-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1f72-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1f72-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1f72-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1f72-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1f72-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1f72-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1f72-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
