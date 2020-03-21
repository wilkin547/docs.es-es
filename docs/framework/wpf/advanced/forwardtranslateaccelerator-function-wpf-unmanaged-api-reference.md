---
title: 'ForwardTranslateAccelerator (función): referencia de API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186630"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="343c0-102">Función ForwardTranslateAccelerator (Referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="343c0-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="343c0-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para usarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="343c0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="343c0-104">Utilizado por la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="343c0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="343c0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="343c0-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="343c0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="343c0-106">Parameters</span></span>  
 <span data-ttu-id="343c0-107">Pmsg</span><span class="sxs-lookup"><span data-stu-id="343c0-107">pMsg</span></span>  
 <span data-ttu-id="343c0-108">Un puntero a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="343c0-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="343c0-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="343c0-109">appUnhandled</span></span>  
 <span data-ttu-id="343c0-110">`true`cuando la aplicación ya tiene la oportunidad de controlar el mensaje de entrada, pero no lo ha manejado; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="343c0-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="343c0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="343c0-111">Requirements</span></span>  
 <span data-ttu-id="343c0-112">**Plataformas:** Consulte Requisitos del sistema de [.NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="343c0-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="343c0-113">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="343c0-113">**DLL:**</span></span>  
  
 <span data-ttu-id="343c0-114">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="343c0-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="343c0-115">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="343c0-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="343c0-116">**Versión de .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="343c0-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343c0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="343c0-117">See also</span></span>

- [<span data-ttu-id="343c0-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="343c0-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
