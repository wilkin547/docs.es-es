---
title: LoadFromHistory Function - Referencia de API no administrada de WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141580"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="935cb-102">Función LoadFromHistory (Referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="935cb-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="935cb-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para usarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="935cb-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="935cb-104">Utilizado por la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="935cb-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935cb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="935cb-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="935cb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="935cb-106">Parameters</span></span>  
 <span data-ttu-id="935cb-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="935cb-107">pHistoryStream</span></span>  
 <span data-ttu-id="935cb-108">Un puntero a una secuencia de información del historial.</span><span class="sxs-lookup"><span data-stu-id="935cb-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="935cb-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="935cb-109">pBindCtx</span></span>  
 <span data-ttu-id="935cb-110">Puntero a un contexto de enlace.</span><span class="sxs-lookup"><span data-stu-id="935cb-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="935cb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="935cb-111">Requirements</span></span>  
 <span data-ttu-id="935cb-112">**Plataformas:** Consulte Requisitos del sistema de [.NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="935cb-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="935cb-113">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="935cb-113">**DLL:**</span></span>  
  
 <span data-ttu-id="935cb-114">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="935cb-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="935cb-115">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="935cb-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="935cb-116">**Versión de .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="935cb-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935cb-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="935cb-117">See also</span></span>

- [<span data-ttu-id="935cb-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="935cb-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
