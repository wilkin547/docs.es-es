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
ms.openlocfilehash: d52f089923d16f93345444c07ff8e0619644f2eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725162"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="d965e-102">IBindingDisplay::GetCurrentDisplay (Método)</span><span class="sxs-lookup"><span data-stu-id="d965e-102">IBindingDisplay::GetCurrentDisplay Method</span></span>

<span data-ttu-id="d965e-103">Devuelve la información de presentación del enlace actual.</span><span class="sxs-lookup"><span data-stu-id="d965e-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d965e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d965e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d965e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d965e-105">Parameters</span></span>  

 `display`  
 <span data-ttu-id="d965e-106">[out, retval] Un puntero a un objeto SafeArray que contiene la información de presentación del enlace.</span><span class="sxs-lookup"><span data-stu-id="d965e-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d965e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d965e-107">Remarks</span></span>  

 <span data-ttu-id="d965e-108">El método [IBindingDisplay:: InitializeForProcess (](ibindingdisplay-initializeforprocess-method.md) debe haber tenido éxito previamente y el programa debe detenerse en un depurador.</span><span class="sxs-lookup"><span data-stu-id="d965e-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="d965e-109">El autor de la llamada debe desasignar la memoria devuelta mediante `SAFEARRAY` [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="d965e-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d965e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d965e-110">Requirements</span></span>  

 <span data-ttu-id="d965e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d965e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d965e-112">**Encabezado:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="d965e-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="d965e-113">**Biblioteca:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="d965e-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="d965e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d965e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d965e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d965e-115">See also</span></span>

- [<span data-ttu-id="d965e-116">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d965e-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="d965e-117">Método InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="d965e-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
