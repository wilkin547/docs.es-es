---
title: "Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: CreateIDispatchSTAForwarder
api_location: PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5139784fdc067c09d032c0bf37114e0eb1caac33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="1b062-102">Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)</span><span class="sxs-lookup"><span data-stu-id="1b062-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="1b062-103">Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="1b062-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="1b062-104">Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y de windows.</span><span class="sxs-lookup"><span data-stu-id="1b062-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b062-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b062-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b062-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b062-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1b062-107">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b062-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="1b062-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="1b062-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="1b062-109">Un puntero a un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="1b062-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="1b062-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="1b062-110">ppForwarder</span></span>  
 <span data-ttu-id="1b062-111">Un puntero a la dirección de un `IDispatch` interfaz.</span><span class="sxs-lookup"><span data-stu-id="1b062-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b062-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b062-112">Requirements</span></span>  
 <span data-ttu-id="1b062-113">**Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b062-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b062-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="1b062-114">**DLL:**</span></span>  
  
 <span data-ttu-id="1b062-115">En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="1b062-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="1b062-116">En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="1b062-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="1b062-117">**Versión de .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b062-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b062-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b062-118">See Also</span></span>  
 [<span data-ttu-id="1b062-119">Referencia de API no administrada de WPF</span><span class="sxs-lookup"><span data-stu-id="1b062-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
