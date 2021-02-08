---
description: 'Más información sobre: IBindingDisplay:: Getcurrentdisplay ((método)'
title: IBindingDisplay::GetCurrentDisplay (Método)
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 680a91c8025ac3247701c14c23f442da5e304ecb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800427"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="fbb70-103">IBindingDisplay::GetCurrentDisplay (Método)</span><span class="sxs-lookup"><span data-stu-id="fbb70-103">IBindingDisplay::GetCurrentDisplay Method</span></span>

<span data-ttu-id="fbb70-104">Devuelve la información de presentación del enlace actual.</span><span class="sxs-lookup"><span data-stu-id="fbb70-104">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbb70-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbb70-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbb70-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fbb70-106">Parameters</span></span>  

 `display`  
 <span data-ttu-id="fbb70-107">[out, retval] Un puntero a un objeto SafeArray que contiene la información de presentación del enlace.</span><span class="sxs-lookup"><span data-stu-id="fbb70-107">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbb70-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fbb70-108">Remarks</span></span>  

 <span data-ttu-id="fbb70-109">El método [IBindingDisplay:: InitializeForProcess (](ibindingdisplay-initializeforprocess-method.md) debe haber tenido éxito previamente y el programa debe detenerse en un depurador.</span><span class="sxs-lookup"><span data-stu-id="fbb70-109">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="fbb70-110">El autor de la llamada debe desasignar la memoria devuelta mediante `SAFEARRAY` [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="fbb70-110">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbb70-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbb70-111">Requirements</span></span>  

 <span data-ttu-id="fbb70-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbb70-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbb70-113">**Encabezado:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="fbb70-113">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="fbb70-114">**Biblioteca:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="fbb70-114">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="fbb70-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbb70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbb70-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbb70-116">See also</span></span>

- [<span data-ttu-id="fbb70-117">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbb70-117">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="fbb70-118">Método InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="fbb70-118">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
