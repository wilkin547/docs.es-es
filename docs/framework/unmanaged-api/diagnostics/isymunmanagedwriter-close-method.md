---
title: "ISymUnmanagedWriter::Close (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 70f710802862c3237cbd67693f8366946926891e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="abfed-102">ISymUnmanagedWriter::Close (Método)</span><span class="sxs-lookup"><span data-stu-id="abfed-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="abfed-103">Cierra el escritor de símbolos después de confirmar los símbolos al almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="abfed-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abfed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abfed-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="abfed-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="abfed-105">Return Value</span></span>  
 <span data-ttu-id="abfed-106">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="abfed-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abfed-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abfed-107">Remarks</span></span>  
 <span data-ttu-id="abfed-108">Después de esta llamada, el escritor de símbolos deja de ser válido para futuras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="abfed-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="abfed-109">Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice el [ISymUnmanagedWriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="abfed-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abfed-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abfed-110">Requirements</span></span>  
 <span data-ttu-id="abfed-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="abfed-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfed-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="abfed-112">See Also</span></span>  
 [<span data-ttu-id="abfed-113">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abfed-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
