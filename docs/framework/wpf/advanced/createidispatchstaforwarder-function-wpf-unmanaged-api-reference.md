---
title: 'Función CreateIDispatchSTAForwarder: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738035"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="63321-102">Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="63321-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="63321-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="63321-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="63321-104">Lo utiliza la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y ventanas.</span><span class="sxs-lookup"><span data-stu-id="63321-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63321-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63321-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="63321-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="63321-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="63321-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63321-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="63321-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="63321-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="63321-109">Puntero a una interfaz de `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="63321-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="63321-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="63321-110">ppForwarder</span></span>  
 <span data-ttu-id="63321-111">Puntero a la dirección de una interfaz de `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="63321-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63321-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="63321-112">Requirements</span></span>  
 <span data-ttu-id="63321-113">**Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63321-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63321-114">**DLL**</span><span class="sxs-lookup"><span data-stu-id="63321-114">**DLL:**</span></span>  
  
 <span data-ttu-id="63321-115">En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="63321-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="63321-116">En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="63321-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="63321-117">**Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63321-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63321-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="63321-118">See also</span></span>

- [<span data-ttu-id="63321-119">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="63321-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
