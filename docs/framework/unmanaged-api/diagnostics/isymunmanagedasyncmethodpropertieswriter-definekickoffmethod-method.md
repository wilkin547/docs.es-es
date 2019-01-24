---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b4564aeb3c8ed4674e755e5691bb0a9d417bca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624201"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="8530a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="8530a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="8530a-103">Establece el método inicial que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="8530a-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8530a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8530a-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8530a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8530a-105">Parameters</span></span>  
  
|<span data-ttu-id="8530a-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8530a-106">Parameter</span></span>|<span data-ttu-id="8530a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8530a-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="8530a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8530a-108">Return Value</span></span>  
 <span data-ttu-id="8530a-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8530a-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8530a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8530a-110">Requirements</span></span>  
 <span data-ttu-id="8530a-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8530a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8530a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8530a-112">See also</span></span>
- [<span data-ttu-id="8530a-113">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8530a-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
