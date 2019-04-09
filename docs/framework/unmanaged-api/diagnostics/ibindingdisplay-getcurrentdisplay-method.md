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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 472e06c3a00762a7bb012fbcb525d8e0b3a9271a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162264"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="0115b-102">IBindingDisplay::GetCurrentDisplay (Método)</span><span class="sxs-lookup"><span data-stu-id="0115b-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="0115b-103">Devuelve la información de visualización del enlace actual.</span><span class="sxs-lookup"><span data-stu-id="0115b-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0115b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0115b-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0115b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0115b-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="0115b-106">[out, retval] Un puntero a una matriz safearray que contiene la información de visualización de enlace.</span><span class="sxs-lookup"><span data-stu-id="0115b-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0115b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0115b-107">Remarks</span></span>  
 <span data-ttu-id="0115b-108">El [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) método debe haberse realizado correctamente y el programa debe ser detenido por un depurador.</span><span class="sxs-lookup"><span data-stu-id="0115b-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="0115b-109">El llamador debe desasignar devuelto `SAFEARRAY` memoria mediante el uso de [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="0115b-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0115b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0115b-110">Requirements</span></span>  
 <span data-ttu-id="0115b-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0115b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0115b-112">**Encabezado**: BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="0115b-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="0115b-113">**Biblioteca:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="0115b-113">**Library:** BindingDisplay.idl</span></span>  
  
 **<span data-ttu-id="0115b-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0115b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0115b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0115b-115">See also</span></span>

- [<span data-ttu-id="0115b-116">IBindingDisplay (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0115b-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="0115b-117">Método InitializeForProcess</span><span class="sxs-lookup"><span data-stu-id="0115b-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
