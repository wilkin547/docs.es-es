---
title: "ISymUnmanagedWriter::Abort (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Abort
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8013bf2118a73a8b5eb8a5b160f2655a83382efc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="4f111-102">ISymUnmanagedWriter::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="4f111-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="4f111-103">Cierra el escritor de símbolos sin confirmar los símbolos al almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="4f111-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="4f111-104">Después de esta llamada, el escritor de símbolos deja de ser válido para futuras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4f111-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="4f111-105">Para confirmar los símbolos y cerrar el escritor de símbolos, utilice el [ISymUnmanagedWriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4f111-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f111-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f111-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4f111-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4f111-107">Return Value</span></span>  
 <span data-ttu-id="4f111-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4f111-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f111-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f111-109">Requirements</span></span>  
 <span data-ttu-id="4f111-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f111-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f111-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f111-111">See Also</span></span>  
 [<span data-ttu-id="4f111-112">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f111-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
