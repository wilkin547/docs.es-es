---
title: ProcessUnhandledException (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 0c8751454be6e0eed547c38e9d0bc7931abaec3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196975"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="16670-102">ProcessUnhandledException (función) (referencia de API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="16670-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="16670-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="16670-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="16670-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="16670-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16670-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16670-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="16670-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16670-106">Parameters</span></span>  
 <span data-ttu-id="16670-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="16670-107">errorMsg</span></span>  
 <span data-ttu-id="16670-108">Mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="16670-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16670-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16670-109">Requirements</span></span>  
 <span data-ttu-id="16670-110">**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16670-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16670-111">**ARCHIVO DLL:**</span><span class="sxs-lookup"><span data-stu-id="16670-111">**DLL:**</span></span>  
  
 <span data-ttu-id="16670-112">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="16670-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="16670-113">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="16670-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="16670-114">**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16670-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16670-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="16670-115">See also</span></span>

- [<span data-ttu-id="16670-116">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="16670-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
