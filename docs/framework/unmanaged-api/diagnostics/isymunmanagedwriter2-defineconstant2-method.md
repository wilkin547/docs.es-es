---
title: "ISymUnmanagedWriter2::DefineConstant2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter2.DefineConstant2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 998916ab485042ba2f8493afe84ea5375f3eb740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="69e35-102">ISymUnmanagedWriter2::DefineConstant2 (Método)</span><span class="sxs-lookup"><span data-stu-id="69e35-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="69e35-103">Define un nombre para un valor constante.</span><span class="sxs-lookup"><span data-stu-id="69e35-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69e35-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69e35-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69e35-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="69e35-106">[in] El nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="69e35-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="69e35-107">[in] El valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="69e35-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="69e35-108">[in] El token de metadatos de la constante.</span><span class="sxs-lookup"><span data-stu-id="69e35-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69e35-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69e35-109">Return Value</span></span>  
 <span data-ttu-id="69e35-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="69e35-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69e35-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69e35-111">Requirements</span></span>  
 <span data-ttu-id="69e35-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69e35-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e35-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="69e35-113">See Also</span></span>  
 [<span data-ttu-id="69e35-114">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69e35-114">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="69e35-115">DefineConstant (método)</span><span class="sxs-lookup"><span data-stu-id="69e35-115">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)
