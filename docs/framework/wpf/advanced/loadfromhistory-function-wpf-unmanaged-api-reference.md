---
title: LoadFromHistory (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: a4480d54390aea2771e2939b0a0825f6c49c3564
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084984"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="503cf-102">LoadFromHistory (función) (referencia de API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="503cf-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="503cf-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="503cf-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="503cf-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.</span><span class="sxs-lookup"><span data-stu-id="503cf-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="503cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="503cf-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="503cf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="503cf-106">Parameters</span></span>  
 <span data-ttu-id="503cf-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="503cf-107">pHistoryStream</span></span>  
 <span data-ttu-id="503cf-108">Un puntero a una secuencia de información de historial.</span><span class="sxs-lookup"><span data-stu-id="503cf-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="503cf-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="503cf-109">pBindCtx</span></span>  
 <span data-ttu-id="503cf-110">Un puntero a un contexto de enlace.</span><span class="sxs-lookup"><span data-stu-id="503cf-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="503cf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="503cf-111">Requirements</span></span>  
 <span data-ttu-id="503cf-112">**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="503cf-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="503cf-113">DLL:</span><span class="sxs-lookup"><span data-stu-id="503cf-113">DLL:</span></span>**  
  
 <span data-ttu-id="503cf-114">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="503cf-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="503cf-115">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="503cf-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="503cf-116">Versión de .NET framework:</span><span class="sxs-lookup"><span data-stu-id="503cf-116">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="503cf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="503cf-117">See also</span></span>

- [<span data-ttu-id="503cf-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="503cf-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
