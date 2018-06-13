---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a476d92486d7f2523dfbcc8b25e9c11e26c55f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425620"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="d0f3d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="d0f3d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="d0f3d-103">Establece el método de inicio que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="d0f3d-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0f3d-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0f3d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0f3d-105">Parameters</span></span>  
  
|<span data-ttu-id="d0f3d-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d0f3d-106">Parameter</span></span>|<span data-ttu-id="d0f3d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0f3d-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="d0f3d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0f3d-108">Return Value</span></span>  
 <span data-ttu-id="d0f3d-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d0f3d-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0f3d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0f3d-110">Requirements</span></span>  
 <span data-ttu-id="d0f3d-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d0f3d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f3d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0f3d-112">See Also</span></span>  
 [<span data-ttu-id="d0f3d-113">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0f3d-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
