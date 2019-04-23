---
title: ISymUnmanagedWriter::Abort (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 090183cad17aff6faf5e79639eadff086c1a26ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119540"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="62b57-102">ISymUnmanagedWriter::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="62b57-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="62b57-103">Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="62b57-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="62b57-104">Después de esta llamada, el escritor de símbolos deja de ser válido para posteriores actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="62b57-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="62b57-105">Para confirmar los símbolos y cerrar el escritor de símbolos, utilice el [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="62b57-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b57-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62b57-106">Syntax</span></span>  
  
```  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="62b57-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62b57-107">Return Value</span></span>  
 <span data-ttu-id="62b57-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="62b57-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62b57-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62b57-109">Requirements</span></span>  
 <span data-ttu-id="62b57-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="62b57-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b57-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="62b57-111">See also</span></span>

- [<span data-ttu-id="62b57-112">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62b57-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
