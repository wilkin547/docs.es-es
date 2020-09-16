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
ms.openlocfilehash: db2474741012c4fd1734adafed112821c42c099c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541713"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="234f4-102">IBindingDisplay::GetCurrentDisplay (Método)</span><span class="sxs-lookup"><span data-stu-id="234f4-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="234f4-103">Devuelve la información de presentación del enlace actual.</span><span class="sxs-lookup"><span data-stu-id="234f4-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="234f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="234f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="234f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="234f4-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="234f4-106">[out, retval] Un puntero a un objeto SafeArray que contiene la información de presentación del enlace.</span><span class="sxs-lookup"><span data-stu-id="234f4-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="234f4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="234f4-107">Remarks</span></span>  
 <span data-ttu-id="234f4-108">El método [IBindingDisplay:: InitializeForProcess (](ibindingdisplay-initializeforprocess-method.md) debe haber tenido éxito previamente y el programa debe detenerse en un depurador.</span><span class="sxs-lookup"><span data-stu-id="234f4-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="234f4-109">El autor de la llamada debe desasignar la memoria devuelta mediante `SAFEARRAY` [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="234f4-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="234f4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="234f4-110">Requirements</span></span>  
 <span data-ttu-id="234f4-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="234f4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="234f4-112">**Encabezado:** BindingDisplay. h</span><span class="sxs-lookup"><span data-stu-id="234f4-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="234f4-113">**Biblioteca:** BindingDisplay. idl</span><span class="sxs-lookup"><span data-stu-id="234f4-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="234f4-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="234f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="234f4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="234f4-115">See also</span></span>

- [<span data-ttu-id="234f4-116">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="234f4-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="234f4-117">Método InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="234f4-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
