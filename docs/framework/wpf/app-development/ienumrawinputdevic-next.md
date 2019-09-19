---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053398"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="cbd6c-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="cbd6c-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="cbd6c-103">Enumera las siguientes `celt` estructuras [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) en la lista del enumerador `rgelt` y las devuelve junto con el número real de elementos enumerados en. `pceltFetched`</span><span class="sxs-lookup"><span data-stu-id="cbd6c-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbd6c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbd6c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cbd6c-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="cbd6c-106">de Número de estructuras [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) devueltas en `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="cbd6c-107">[out] Matriz de tamaño celt (o superior) para recibir estructuras RAWINPUTDEVICE enumeradas.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="cbd6c-108">[out] Puntero al número de elementos proporcionados realmente en `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="cbd6c-109">El llamador puede pasar `NULL` si `rgelt` es uno.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="cbd6c-110">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cbd6c-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="cbd6c-111">HRESULT: S_OK si el número de elementos proporcionado es `celt`; S_FALSE en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
