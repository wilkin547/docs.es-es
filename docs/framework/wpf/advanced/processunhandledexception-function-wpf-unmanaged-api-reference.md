---
title: "Función ProcessUnhandledException (referencia de la API no administrada de WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ProcessUnhandledException
api_location: PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8328ae4bcbff54743e8df0a4b6ff6da3065ea470
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b9170-102">Función ProcessUnhandledException (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="b9170-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="b9170-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="b9170-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="b9170-104">Utiliza la infraestructura de Windows Presentation Foundation (WPF) para el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="b9170-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9170-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9170-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9170-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9170-106">Parameters</span></span>  
 <span data-ttu-id="b9170-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="b9170-107">errorMsg</span></span>  
 <span data-ttu-id="b9170-108">Mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b9170-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9170-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9170-109">Requirements</span></span>  
 <span data-ttu-id="b9170-110">**Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9170-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9170-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="b9170-111">**DLL:**</span></span>  
  
 <span data-ttu-id="b9170-112">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="b9170-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="b9170-113">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="b9170-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="b9170-114">**Versión de .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9170-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9170-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9170-115">See Also</span></span>  
 [<span data-ttu-id="b9170-116">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="b9170-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
