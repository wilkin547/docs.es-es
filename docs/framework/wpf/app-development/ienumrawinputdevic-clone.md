---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053420"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="d9cd3-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="d9cd3-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="d9cd3-103">Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9cd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9cd3-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9cd3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9cd3-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="d9cd3-106">enuncia Dirección de la variable de salida que recibe el puntero de la interfaz [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) .</span><span class="sxs-lookup"><span data-stu-id="d9cd3-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="d9cd3-107">Si el método no se realiza correctamente, el valor de esta variable de salida es indefinido.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d9cd3-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9cd3-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="d9cd3-109">HRESULT: Este método admite los valores devueltos estándar E_INVALIDARG, E_OUTOFMEMORY y E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9cd3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9cd3-110">Remarks</span></span>  
 <span data-ttu-id="d9cd3-111">Este método permite grabar un punto en la secuencia de enumeración para volver a ese punto en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="d9cd3-112">El llamador debe liberar este nuevo enumerador por separado del primer enumerador.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
