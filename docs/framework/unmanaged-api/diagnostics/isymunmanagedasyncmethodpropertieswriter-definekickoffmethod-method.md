---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129173"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="859de-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="859de-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="859de-103">Establece el método de inicio que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="859de-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="859de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="859de-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="859de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="859de-105">Parameters</span></span>  
  
|<span data-ttu-id="859de-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="859de-106">Parameter</span></span>|<span data-ttu-id="859de-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="859de-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="859de-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="859de-108">Return Value</span></span>  
 <span data-ttu-id="859de-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="859de-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="859de-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="859de-110">Requirements</span></span>  
 <span data-ttu-id="859de-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="859de-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859de-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="859de-112">See also</span></span>

- [<span data-ttu-id="859de-113">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="859de-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
