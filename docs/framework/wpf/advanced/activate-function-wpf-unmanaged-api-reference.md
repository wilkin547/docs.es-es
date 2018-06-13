---
title: Activar la función (referencia de la API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 4931f64a525f14ad5b0b69c582a81cd15d98e541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539058"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f5923-102">Activar la función (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="f5923-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="f5923-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="f5923-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="f5923-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.</span><span class="sxs-lookup"><span data-stu-id="f5923-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5923-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5923-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5923-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5923-106">Parameters</span></span>  
 <span data-ttu-id="f5923-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="f5923-107">pParameters</span></span>  
 <span data-ttu-id="f5923-108">Un puntero a los parámetros de activación de la ventana.</span><span class="sxs-lookup"><span data-stu-id="f5923-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="f5923-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="f5923-109">ppInner</span></span>  
 <span data-ttu-id="f5923-110">Un puntero a la dirección de un búfer único elemento que contiene un puntero a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="f5923-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5923-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5923-111">Requirements</span></span>  
 <span data-ttu-id="f5923-112">**Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5923-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5923-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="f5923-113">**DLL:**</span></span>  
  
 <span data-ttu-id="f5923-114">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="f5923-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="f5923-115">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="f5923-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="f5923-116">**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5923-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5923-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5923-117">See Also</span></span>  
 [<span data-ttu-id="f5923-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="f5923-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
