---
title: IBindingDisplay::InitializeForProcess (Método)
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa1e85751f90c34d40e88207af5c7eed2dd1bb82
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197885"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="abc95-102">IBindingDisplay::InitializeForProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="abc95-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="abc95-103">Inicializa el [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="abc95-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abc95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abc95-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abc95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abc95-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="abc95-106">[in] El identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="abc95-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abc95-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abc95-107">Remarks</span></span>  
 <span data-ttu-id="abc95-108">El depurador llama el `InitializeForProcess` método en tiempo de creación para inicializar la presentación de enlace.</span><span class="sxs-lookup"><span data-stu-id="abc95-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> `InitializeForProcess` <span data-ttu-id="abc95-109">se debe llamar en tiempo de creación antes de cualquier otro método en `IBindingDisplay` se llama.</span><span class="sxs-lookup"><span data-stu-id="abc95-109">must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abc95-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abc95-110">Requirements</span></span>  
 <span data-ttu-id="abc95-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abc95-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abc95-112">**Encabezado**: BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="abc95-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="abc95-113">**Biblioteca:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="abc95-113">**Library:** BindingDisplay.idl</span></span>  
  
 **<span data-ttu-id="abc95-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="abc95-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="abc95-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="abc95-115">See also</span></span>

- [<span data-ttu-id="abc95-116">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="abc95-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
