---
title: 'Función LoadFromHistory: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727933"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="354b5-102">Función LoadFromHistory (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="354b5-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="354b5-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="354b5-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="354b5-104">Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="354b5-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="354b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="354b5-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="354b5-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="354b5-106">Parameters</span></span>  
 <span data-ttu-id="354b5-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="354b5-107">pHistoryStream</span></span>  
 <span data-ttu-id="354b5-108">Un puntero a un flujo de información del historial.</span><span class="sxs-lookup"><span data-stu-id="354b5-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="354b5-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="354b5-109">pBindCtx</span></span>  
 <span data-ttu-id="354b5-110">Un puntero a un contexto de enlace.</span><span class="sxs-lookup"><span data-stu-id="354b5-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="354b5-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="354b5-111">Requirements</span></span>  
 <span data-ttu-id="354b5-112">**Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="354b5-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="354b5-113">**DLL**</span><span class="sxs-lookup"><span data-stu-id="354b5-113">**DLL:**</span></span>  
  
 <span data-ttu-id="354b5-114">En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="354b5-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="354b5-115">En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="354b5-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="354b5-116">**Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="354b5-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354b5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="354b5-117">See also</span></span>

- [<span data-ttu-id="354b5-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="354b5-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
