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
ms.openlocfilehash: c19b49e9e9d4e388706a96ff54d588d5aeff99b3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775948"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="ece03-102">IBindingDisplay::InitializeForProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="ece03-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="ece03-103">Inicializa el [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="ece03-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece03-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ece03-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ece03-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ece03-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="ece03-106">[in] El identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="ece03-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ece03-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ece03-107">Remarks</span></span>  
 <span data-ttu-id="ece03-108">El depurador llama el `InitializeForProcess` método en tiempo de creación para inicializar la presentación de enlace.</span><span class="sxs-lookup"><span data-stu-id="ece03-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="ece03-109">`InitializeForProcess` se debe llamar en tiempo de creación antes de cualquier otro método en `IBindingDisplay` se llama.</span><span class="sxs-lookup"><span data-stu-id="ece03-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece03-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ece03-110">Requirements</span></span>  
 <span data-ttu-id="ece03-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ece03-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ece03-112">**Encabezado**: BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="ece03-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="ece03-113">**Biblioteca:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="ece03-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="ece03-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ece03-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ece03-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ece03-115">See also</span></span>

- [<span data-ttu-id="ece03-116">IBindingDisplay (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ece03-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
