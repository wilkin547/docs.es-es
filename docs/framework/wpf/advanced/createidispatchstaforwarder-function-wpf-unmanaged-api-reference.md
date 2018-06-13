---
title: Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7e45d5cafa40ba147fe39888e74a67ac9f95c5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536656"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e5b2d-102">Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="e5b2d-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e5b2d-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="e5b2d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e5b2d-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y de windows.</span><span class="sxs-lookup"><span data-stu-id="e5b2d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b2d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5b2d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5b2d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5b2d-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e5b2d-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5b2d-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="e5b2d-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="e5b2d-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="e5b2d-109">Un puntero a un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="e5b2d-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="e5b2d-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="e5b2d-110">ppForwarder</span></span>  
 <span data-ttu-id="e5b2d-111">Un puntero a la dirección de un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="e5b2d-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b2d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5b2d-112">Requirements</span></span>  
 <span data-ttu-id="e5b2d-113">**Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5b2d-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b2d-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="e5b2d-114">**DLL:**</span></span>  
  
 <span data-ttu-id="e5b2d-115">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="e5b2d-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e5b2d-116">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="e5b2d-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e5b2d-117">**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b2d-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b2d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5b2d-118">See Also</span></span>  
 [<span data-ttu-id="e5b2d-119">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="e5b2d-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
