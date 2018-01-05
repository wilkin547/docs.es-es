---
title: "Función ForwardTranslateAccelerator (referencia de la API no administrada de WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cca9c78eaf13e04d22fce9f61ce4a7ab9ee09769
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e40d3-102">Función ForwardTranslateAccelerator (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="e40d3-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e40d3-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="e40d3-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e40d3-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.</span><span class="sxs-lookup"><span data-stu-id="e40d3-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e40d3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e40d3-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e40d3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e40d3-106">Parameters</span></span>  
 <span data-ttu-id="e40d3-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="e40d3-107">pMsg</span></span>  
 <span data-ttu-id="e40d3-108">Un puntero a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="e40d3-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="e40d3-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="e40d3-109">appUnhandled</span></span>  
 <span data-ttu-id="e40d3-110">`true`Cuando la aplicación ya tiene una oportunidad para controlar el mensaje de entrada, pero no ha controlado en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e40d3-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e40d3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e40d3-111">Requirements</span></span>  
 <span data-ttu-id="e40d3-112">**Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e40d3-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e40d3-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="e40d3-113">**DLL:**</span></span>  
  
 <span data-ttu-id="e40d3-114">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="e40d3-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e40d3-115">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="e40d3-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e40d3-116">**Versión de .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e40d3-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40d3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e40d3-117">See Also</span></span>  
 [<span data-ttu-id="e40d3-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="e40d3-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
