---
title: Función ProcessUnhandledException (referencia de la API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: bcde3fe6d3fdc1749f29a5c9f7625f802dd49535
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544529"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="53325-102">Función ProcessUnhandledException (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="53325-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="53325-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="53325-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="53325-104">Utiliza la infraestructura de Windows Presentation Foundation (WPF) para el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="53325-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53325-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53325-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53325-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53325-106">Parameters</span></span>  
 <span data-ttu-id="53325-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="53325-107">errorMsg</span></span>  
 <span data-ttu-id="53325-108">Mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="53325-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53325-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53325-109">Requirements</span></span>  
 <span data-ttu-id="53325-110">**Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53325-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53325-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="53325-111">**DLL:**</span></span>  
  
 <span data-ttu-id="53325-112">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="53325-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="53325-113">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="53325-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="53325-114">**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53325-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53325-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="53325-115">See Also</span></span>  
 [<span data-ttu-id="53325-116">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="53325-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
