---
title: Activate (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357279"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="54fc1-102">Activate (función) (referencia de API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="54fc1-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="54fc1-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="54fc1-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="54fc1-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.</span><span class="sxs-lookup"><span data-stu-id="54fc1-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54fc1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54fc1-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54fc1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54fc1-106">Parameters</span></span>  
 <span data-ttu-id="54fc1-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="54fc1-107">pParameters</span></span>  
 <span data-ttu-id="54fc1-108">Un puntero a los parámetros de activación de la ventana.</span><span class="sxs-lookup"><span data-stu-id="54fc1-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="54fc1-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="54fc1-109">ppInner</span></span>  
 <span data-ttu-id="54fc1-110">Un puntero a la dirección de un búfer único elemento que contiene un puntero a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="54fc1-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54fc1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54fc1-111">Requirements</span></span>  
 <span data-ttu-id="54fc1-112">**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54fc1-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54fc1-113">**ARCHIVO DLL:**</span><span class="sxs-lookup"><span data-stu-id="54fc1-113">**DLL:**</span></span>  
  
 <span data-ttu-id="54fc1-114">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="54fc1-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="54fc1-115">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="54fc1-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="54fc1-116">**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54fc1-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fc1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="54fc1-117">See also</span></span>
- [<span data-ttu-id="54fc1-118">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="54fc1-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
