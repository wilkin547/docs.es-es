---
title: 'Función ProcessUnhandledException: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743918"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="42810-102">Función ProcessUnhandledException (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="42810-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="42810-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="42810-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="42810-104">Lo utiliza la infraestructura de Windows Presentation Foundation (WPF) para el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="42810-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42810-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42810-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="42810-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42810-106">Parameters</span></span>  
 <span data-ttu-id="42810-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="42810-107">errorMsg</span></span>  
 <span data-ttu-id="42810-108">El mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="42810-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42810-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42810-109">Requirements</span></span>  
 <span data-ttu-id="42810-110">**Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42810-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42810-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="42810-111">**DLL:**</span></span>  
  
 <span data-ttu-id="42810-112">En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="42810-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="42810-113">En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="42810-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="42810-114">**Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42810-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42810-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42810-115">See also</span></span>

- [<span data-ttu-id="42810-116">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="42810-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
