---
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
ms.openlocfilehash: 9294dbf1caddd4b607185de54efd2b4764e6ca35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448495"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="36bc5-102">IBindingDisplay::GetCurrentDisplay (Método)</span><span class="sxs-lookup"><span data-stu-id="36bc5-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="36bc5-103">Devuelve la información de presentación del enlace actual.</span><span class="sxs-lookup"><span data-stu-id="36bc5-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36bc5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36bc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36bc5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36bc5-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="36bc5-106">[out, retval] Un puntero a un objeto SafeArray que contiene la información de presentación del enlace.</span><span class="sxs-lookup"><span data-stu-id="36bc5-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36bc5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36bc5-107">Remarks</span></span>  
 <span data-ttu-id="36bc5-108">El método [IBindingDisplay:: InitializeForProcess (](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) debe haber tenido éxito previamente y el programa debe detenerse en un depurador.</span><span class="sxs-lookup"><span data-stu-id="36bc5-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="36bc5-109">El autor de la llamada debe desasignar la memoria `SAFEARRAY` devuelta mediante [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="36bc5-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36bc5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36bc5-110">Requirements</span></span>  
 <span data-ttu-id="36bc5-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36bc5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36bc5-112">**Encabezado:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="36bc5-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="36bc5-113">**Biblioteca:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="36bc5-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="36bc5-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36bc5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36bc5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="36bc5-115">See also</span></span>

- [<span data-ttu-id="36bc5-116">IBindingDisplay (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36bc5-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="36bc5-117">InitializeForProcess (método)</span><span class="sxs-lookup"><span data-stu-id="36bc5-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
