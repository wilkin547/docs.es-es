---
title: 'Función ForwardTranslateAccelerator: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747039"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="6e4c5-102">Función ForwardTranslateAccelerator (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="6e4c5-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="6e4c5-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="6e4c5-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="6e4c5-104">Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="6e4c5-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e4c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e4c5-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e4c5-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="6e4c5-106">Parameters</span></span>  
 <span data-ttu-id="6e4c5-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="6e4c5-107">pMsg</span></span>  
 <span data-ttu-id="6e4c5-108">Un puntero a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="6e4c5-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="6e4c5-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="6e4c5-109">appUnhandled</span></span>  
 <span data-ttu-id="6e4c5-110">`true` cuando la aplicación ya tiene la oportunidad de controlar el mensaje de entrada, pero no la ha controlado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="6e4c5-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e4c5-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6e4c5-111">Requirements</span></span>  
 <span data-ttu-id="6e4c5-112">**Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e4c5-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e4c5-113">**DLL**</span><span class="sxs-lookup"><span data-stu-id="6e4c5-113">**DLL:**</span></span>  
  
 <span data-ttu-id="6e4c5-114">En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="6e4c5-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="6e4c5-115">En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="6e4c5-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="6e4c5-116">**Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e4c5-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4c5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e4c5-117">See also</span></span>

- [<span data-ttu-id="6e4c5-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="6e4c5-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
