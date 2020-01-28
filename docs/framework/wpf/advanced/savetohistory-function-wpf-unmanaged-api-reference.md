---
title: 'Función SaveToHistory: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 7337e5dc23a3dce5de8270902bce228c49bc6edb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731747"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="88535-102">Función SaveToHistory (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="88535-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="88535-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="88535-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="88535-104">Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="88535-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88535-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88535-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="88535-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="88535-106">Parameters</span></span>  
 <span data-ttu-id="88535-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="88535-107">pHistoryStream</span></span>  
 <span data-ttu-id="88535-108">Puntero a la secuencia del historial.</span><span class="sxs-lookup"><span data-stu-id="88535-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88535-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="88535-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88535-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="88535-110">Requirements</span></span>  
 <span data-ttu-id="88535-111">**Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88535-111">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88535-112">**DLL**</span><span class="sxs-lookup"><span data-stu-id="88535-112">**DLL:**</span></span>  
  
 <span data-ttu-id="88535-113">En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="88535-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="88535-114">En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="88535-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="88535-115">**Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88535-115">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88535-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="88535-116">See also</span></span>

- [<span data-ttu-id="88535-117">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="88535-117">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
