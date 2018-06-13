---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 3cf3231bd48290c5b6b0ce8eeb6534de564c0c85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546411"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="57737-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="57737-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="57737-103">Enumera la siguiente `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) estructuras en la lista del enumerador, devolverlas en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="57737-103">Enumerates the next `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57737-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57737-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57737-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57737-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="57737-106">[in] Número de [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) se devuelven en estructuras `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="57737-106">[in] Number of [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="57737-107">[out] Matriz de tamaño celt (o superior) para recibir estructuras RAWINPUTDEVICE enumeradas.</span><span class="sxs-lookup"><span data-stu-id="57737-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="57737-108">[out] Puntero al número de elementos proporcionados realmente en `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="57737-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="57737-109">El llamador puede pasar `NULL` si `rgelt` es uno.</span><span class="sxs-lookup"><span data-stu-id="57737-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="57737-110">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="57737-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="57737-111">HRESULT: S_OK si el número de elementos proporcionado es `celt`. En caso contrario, S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="57737-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
