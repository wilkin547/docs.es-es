---
title: CreateIDispatchSTAForwarder (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: a89b29cd459060c93d5ca77bb2154e1a10b02d03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213655"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="04f5a-102">CreateIDispatchSTAForwarder (función) (referencia de API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="04f5a-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="04f5a-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="04f5a-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="04f5a-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y windows.</span><span class="sxs-lookup"><span data-stu-id="04f5a-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f5a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04f5a-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f5a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04f5a-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="04f5a-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04f5a-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="04f5a-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="04f5a-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="04f5a-109">Un puntero a un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="04f5a-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="04f5a-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="04f5a-110">ppForwarder</span></span>  
 <span data-ttu-id="04f5a-111">Un puntero a la dirección de un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="04f5a-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f5a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04f5a-112">Requirements</span></span>  
 <span data-ttu-id="04f5a-113">**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04f5a-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="04f5a-114">DLL:</span><span class="sxs-lookup"><span data-stu-id="04f5a-114">DLL:</span></span>**  
  
 <span data-ttu-id="04f5a-115">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="04f5a-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="04f5a-116">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="04f5a-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="04f5a-117">Versión de .NET framework:</span><span class="sxs-lookup"><span data-stu-id="04f5a-117">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04f5a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="04f5a-118">See also</span></span>

- [<span data-ttu-id="04f5a-119">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="04f5a-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
