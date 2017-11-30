---
title: "ISymUnmanagedWriter3::OpenMethod2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3.OpenMethod2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1124eac951e32dbf1cedb7926f582ec6abb99007
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="72e99-102">ISymUnmanagedWriter3::OpenMethod2 (Método)</span><span class="sxs-lookup"><span data-stu-id="72e99-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>
<span data-ttu-id="72e99-103">Abre un método y proporciona su desplazamiento de sección real en la imagen.</span><span class="sxs-lookup"><span data-stu-id="72e99-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72e99-104">Syntax</span></span>  
  
```  
HRESULT OpenMethod2(   
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72e99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72e99-105">Parameters</span></span>  
 `method`  
 <span data-ttu-id="72e99-106">[in] El token de metadatos para el método que se abran.</span><span class="sxs-lookup"><span data-stu-id="72e99-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="72e99-107">[in] El desplazamiento de la sección en la imagen.</span><span class="sxs-lookup"><span data-stu-id="72e99-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="72e99-108">[in] El desplazamiento en la imagen.</span><span class="sxs-lookup"><span data-stu-id="72e99-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72e99-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72e99-109">Return Value</span></span>  
 <span data-ttu-id="72e99-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="72e99-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72e99-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72e99-111">Requirements</span></span>  
 <span data-ttu-id="72e99-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72e99-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e99-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="72e99-113">See Also</span></span>  
 [<span data-ttu-id="72e99-114">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72e99-114">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 [<span data-ttu-id="72e99-115">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="72e99-115">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
