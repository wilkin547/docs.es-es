---
title: ForwardTranslateAccelerator (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 4bb7e665bb836dc5f95b14f39179f1d4b9f8173d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080259"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="77cde-102">ForwardTranslateAccelerator (función) (referencia de API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="77cde-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="77cde-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="77cde-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="77cde-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.</span><span class="sxs-lookup"><span data-stu-id="77cde-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77cde-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77cde-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="77cde-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77cde-106">Parameters</span></span>  
 <span data-ttu-id="77cde-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="77cde-107">pMsg</span></span>  
 <span data-ttu-id="77cde-108">Un puntero a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="77cde-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="77cde-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="77cde-109">appUnhandled</span></span>  
 `true` <span data-ttu-id="77cde-110">Cuando la aplicación ya se asignó una oportunidad para controlar el mensaje de entrada, pero no ha controlado en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="77cde-110">when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77cde-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77cde-111">Requirements</span></span>  
 <span data-ttu-id="77cde-112">**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77cde-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="77cde-113">DLL:</span><span class="sxs-lookup"><span data-stu-id="77cde-113">DLL:</span></span>**  
  
 <span data-ttu-id="77cde-114">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="77cde-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="77cde-115">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="77cde-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="77cde-116">Versión de .NET framework:</span><span class="sxs-lookup"><span data-stu-id="77cde-116">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77cde-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="77cde-117">See also</span></span>

- [<span data-ttu-id="77cde-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="77cde-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
