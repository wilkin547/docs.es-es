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
ms.openlocfilehash: 09f39d3b6486e2ec3c04c5d1858a85ce56895527
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610163"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="a2b0d-102">ISymUnmanagedWriter::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="a2b0d-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="a2b0d-103">Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="a2b0d-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="a2b0d-104">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="a2b0d-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="a2b0d-105">Para confirmar los símbolos y cerrar el escritor de símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a2b0d-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b0d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2b0d-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a2b0d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a2b0d-107">Return Value</span></span>  
 <span data-ttu-id="a2b0d-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a2b0d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2b0d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2b0d-109">Requirements</span></span>  
 <span data-ttu-id="a2b0d-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a2b0d-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b0d-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a2b0d-111">See also</span></span>

- [<span data-ttu-id="a2b0d-112">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2b0d-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
