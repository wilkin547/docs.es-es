---
title: CreateIDispatchSTAForwarder Function - Referencia de API no administrada de WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174724"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b3f68-102">Función CreateIDispatchSTAForwarder (Referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="b3f68-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="b3f68-103">Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para usarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="b3f68-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="b3f68-104">Utilizado por la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y ventanas.</span><span class="sxs-lookup"><span data-stu-id="b3f68-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f68-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3f68-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3f68-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3f68-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b3f68-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b3f68-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="b3f68-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="b3f68-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="b3f68-109">Un puntero `IDispatch` a una interfaz.</span><span class="sxs-lookup"><span data-stu-id="b3f68-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="b3f68-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="b3f68-110">ppForwarder</span></span>  
 <span data-ttu-id="b3f68-111">Un puntero a la `IDispatch` dirección de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="b3f68-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3f68-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3f68-112">Requirements</span></span>  
 <span data-ttu-id="b3f68-113">**Plataformas:** Consulte Requisitos del sistema de [.NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3f68-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f68-114">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="b3f68-114">**DLL:**</span></span>  
  
 <span data-ttu-id="b3f68-115">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="b3f68-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="b3f68-116">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="b3f68-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="b3f68-117">**Versión de .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f68-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f68-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3f68-118">See also</span></span>

- [<span data-ttu-id="b3f68-119">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="b3f68-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
