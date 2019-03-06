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
ms.openlocfilehash: c4da322bf779e084f12529d0da6949ef6ada5cf3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379658"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="610b0-102">CreateIDispatchSTAForwarder (función) (referencia de API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="610b0-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="610b0-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="610b0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="610b0-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y windows.</span><span class="sxs-lookup"><span data-stu-id="610b0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="610b0-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="610b0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="610b0-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="610b0-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="610b0-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="610b0-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="610b0-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="610b0-109">Un puntero a un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="610b0-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="610b0-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="610b0-110">ppForwarder</span></span>  
 <span data-ttu-id="610b0-111">Un puntero a la dirección de un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="610b0-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="610b0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="610b0-112">Requirements</span></span>  
 <span data-ttu-id="610b0-113">**Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="610b0-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="610b0-114">**ARCHIVO DLL:**</span><span class="sxs-lookup"><span data-stu-id="610b0-114">**DLL:**</span></span>  
  
 <span data-ttu-id="610b0-115">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="610b0-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="610b0-116">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="610b0-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="610b0-117">**Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="610b0-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610b0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="610b0-118">See also</span></span>
- [<span data-ttu-id="610b0-119">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="610b0-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
