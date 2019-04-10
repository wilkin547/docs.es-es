---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce3c135e031d0c8425e990811fedc40f4ec45243
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226617"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="b2498-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="b2498-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="b2498-103">Establece el método inicial que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b2498-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2498-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2498-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2498-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2498-105">Parameters</span></span>  
  
|<span data-ttu-id="b2498-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b2498-106">Parameter</span></span>|<span data-ttu-id="b2498-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2498-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="b2498-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2498-108">Return Value</span></span>  
 <span data-ttu-id="b2498-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="b2498-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2498-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2498-110">Requirements</span></span>  
 <span data-ttu-id="b2498-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2498-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2498-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2498-112">See also</span></span>

- [<span data-ttu-id="b2498-113">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2498-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
