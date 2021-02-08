---
description: 'Más información sobre: IBindingDisplay:: InitializeForProcess ((método)'
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
ms.openlocfilehash: cf7f0f4d057659089bd7da173e5fac98a7c00dad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800417"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="d4529-103">IBindingDisplay::InitializeForProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="d4529-103">IBindingDisplay::InitializeForProcess Method</span></span>

<span data-ttu-id="d4529-104">Inicializa el objeto [IBindingDisplay](ibindingdisplay-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d4529-104">Initializes the [IBindingDisplay](ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4529-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4529-105">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4529-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4529-106">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="d4529-107">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="d4529-107">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4529-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4529-108">Remarks</span></span>  

 <span data-ttu-id="d4529-109">El depurador llama al `InitializeForProcess` método en el momento de la creación para inicializar la presentación del enlace.</span><span class="sxs-lookup"><span data-stu-id="d4529-109">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="d4529-110">`InitializeForProcess` se debe llamar a en el momento de la creación antes de llamar a cualquier otro método en `IBindingDisplay` .</span><span class="sxs-lookup"><span data-stu-id="d4529-110">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4529-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4529-111">Requirements</span></span>  

 <span data-ttu-id="d4529-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4529-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4529-113">**Encabezado:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="d4529-113">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="d4529-114">**Biblioteca:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="d4529-114">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="d4529-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4529-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4529-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4529-116">See also</span></span>

- [<span data-ttu-id="d4529-117">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4529-117">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
