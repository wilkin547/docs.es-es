---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: abc8a6e4780c8fe50afcf1b04f7e14aeb6452704
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485413"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="619f1-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="619f1-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="619f1-103">Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.</span><span class="sxs-lookup"><span data-stu-id="619f1-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="619f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="619f1-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="619f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="619f1-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="619f1-106">[out] Dirección de variable de salida que recibe el [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="619f1-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="619f1-107">Si el método se realiza correctamente, el valor de esta variable de salida es indefinido.</span><span class="sxs-lookup"><span data-stu-id="619f1-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="619f1-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="619f1-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="619f1-109">HRESULT: Este método admite los valores devueltos estándar E_INVALIDARG y E_OUTOFMEMORY, E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="619f1-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="619f1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="619f1-110">Remarks</span></span>  
 <span data-ttu-id="619f1-111">Este método permite registrar un punto en la secuencia de enumeración con el fin de volver a ese punto en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="619f1-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="619f1-112">El llamador debe liberar este nuevo enumerador por separado desde el primer enumerador.</span><span class="sxs-lookup"><span data-stu-id="619f1-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
