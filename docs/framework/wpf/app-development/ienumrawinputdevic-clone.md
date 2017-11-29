---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f3c00f3a0efd41c425ba29f8465a73e78d624c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="935ad-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="935ad-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="935ad-103">Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.</span><span class="sxs-lookup"><span data-stu-id="935ad-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="935ad-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="935ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="935ad-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="935ad-106">[out] Dirección de la variable de salida que recibe la [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="935ad-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="935ad-107">Si el método es incorrecto, el valor de esta variable de salida es indefinido.</span><span class="sxs-lookup"><span data-stu-id="935ad-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="935ad-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="935ad-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="935ad-109">HRESULT: Este método es compatible con los valores devueltos estándares E_INVALIDARG y E_OUTOFMEMORY, E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="935ad-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="935ad-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="935ad-110">Remarks</span></span>  
 <span data-ttu-id="935ad-111">Este método permite grabar un punto en la secuencia de enumeración con el fin de volver a ese punto en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="935ad-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="935ad-112">El llamador debe liberar este nuevo enumerador por separado desde el primer enumerador.</span><span class="sxs-lookup"><span data-stu-id="935ad-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
