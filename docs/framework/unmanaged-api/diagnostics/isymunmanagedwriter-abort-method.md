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
ms.openlocfilehash: 2136eb32f147b8928e6ac90b99bbdf66804f244d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733274"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="b4f82-102">ISymUnmanagedWriter::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="b4f82-102">ISymUnmanagedWriter::Abort Method</span></span>

<span data-ttu-id="b4f82-103">Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="b4f82-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="b4f82-104">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="b4f82-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="b4f82-105">Para confirmar los símbolos y cerrar el escritor de símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b4f82-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f82-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4f82-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b4f82-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4f82-107">Return Value</span></span>  

 <span data-ttu-id="b4f82-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b4f82-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f82-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4f82-109">Requirements</span></span>  

 <span data-ttu-id="b4f82-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b4f82-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f82-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4f82-111">See also</span></span>

- [<span data-ttu-id="b4f82-112">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4f82-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
