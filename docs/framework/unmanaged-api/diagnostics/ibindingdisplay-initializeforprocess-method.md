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
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442155"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="65a2f-102">IBindingDisplay::InitializeForProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="65a2f-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="65a2f-103">Inicializa el objeto [IBindingDisplay](ibindingdisplay-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="65a2f-103">Initializes the [IBindingDisplay](ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65a2f-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65a2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65a2f-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="65a2f-106">de Identificador del proceso.</span><span class="sxs-lookup"><span data-stu-id="65a2f-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65a2f-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="65a2f-107">Remarks</span></span>  
 <span data-ttu-id="65a2f-108">El depurador llama al `InitializeForProcess` método en el momento de la creación para inicializar la presentación del enlace.</span><span class="sxs-lookup"><span data-stu-id="65a2f-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="65a2f-109">`InitializeForProcess`se debe llamar a en el momento de la creación antes de llamar a cualquier otro método en `IBindingDisplay` .</span><span class="sxs-lookup"><span data-stu-id="65a2f-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a2f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65a2f-110">Requirements</span></span>  
 <span data-ttu-id="65a2f-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a2f-112">**Encabezado:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="65a2f-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="65a2f-113">**Biblioteca:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="65a2f-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="65a2f-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a2f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a2f-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="65a2f-115">See also</span></span>

- [<span data-ttu-id="65a2f-116">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65a2f-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
