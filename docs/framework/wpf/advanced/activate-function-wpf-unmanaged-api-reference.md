---
title: 'Función de activación: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734513"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="89ed5-102">Función Activate (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="89ed5-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="89ed5-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="89ed5-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="89ed5-104">Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="89ed5-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="89ed5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89ed5-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="89ed5-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="89ed5-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="89ed5-107">Puntero a los parámetros de activación de la ventana.</span><span class="sxs-lookup"><span data-stu-id="89ed5-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="89ed5-108">Puntero a la dirección de un búfer de un solo elemento que contiene un puntero a un objeto <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>.</span><span class="sxs-lookup"><span data-stu-id="89ed5-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="89ed5-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="89ed5-109">Requirements</span></span>

<span data-ttu-id="89ed5-110">**Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89ed5-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="89ed5-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="89ed5-111">**DLL:**</span></span>

<span data-ttu-id="89ed5-112">En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="89ed5-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="89ed5-113">En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="89ed5-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="89ed5-114">**Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89ed5-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="89ed5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="89ed5-115">See also</span></span>

- [<span data-ttu-id="89ed5-116">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="89ed5-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
