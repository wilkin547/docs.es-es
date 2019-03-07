---
title: Activate (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480785"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="59739-102">Activate (función) (referencia de API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="59739-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="59739-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="59739-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="59739-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.</span><span class="sxs-lookup"><span data-stu-id="59739-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="59739-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59739-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="59739-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59739-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="59739-107">Un puntero a los parámetros de activación de la ventana.</span><span class="sxs-lookup"><span data-stu-id="59739-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="59739-108">Un puntero a la dirección de un búfer único elemento que contiene un puntero a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="59739-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="59739-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59739-109">Requirements</span></span>

<span data-ttu-id="59739-110">**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59739-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="59739-111">**ARCHIVO DLL:**</span><span class="sxs-lookup"><span data-stu-id="59739-111">**DLL:**</span></span>

<span data-ttu-id="59739-112">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="59739-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="59739-113">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="59739-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="59739-114">**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59739-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="59739-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="59739-115">See also</span></span>

- [<span data-ttu-id="59739-116">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="59739-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
