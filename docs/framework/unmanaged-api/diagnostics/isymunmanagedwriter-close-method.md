---
title: ISymUnmanagedWriter::Close (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd7131c55f9c06a8fcfc0cad859c18e410169c78
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778195"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="8f5a5-102">ISymUnmanagedWriter::Close (Método)</span><span class="sxs-lookup"><span data-stu-id="8f5a5-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="8f5a5-103">Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="8f5a5-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f5a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f5a5-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8f5a5-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8f5a5-105">Return Value</span></span>  
 <span data-ttu-id="8f5a5-106">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8f5a5-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f5a5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f5a5-107">Remarks</span></span>  
 <span data-ttu-id="8f5a5-108">Después de esta llamada, el escritor de símbolos deja de ser válido para posteriores actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="8f5a5-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="8f5a5-109">Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice el [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="8f5a5-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f5a5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f5a5-110">Requirements</span></span>  
 <span data-ttu-id="8f5a5-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8f5a5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f5a5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f5a5-112">See also</span></span>

- [<span data-ttu-id="8f5a5-113">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f5a5-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
