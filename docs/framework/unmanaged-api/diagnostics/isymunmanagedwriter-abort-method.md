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
ms.openlocfilehash: 6074ec5248d27b1405d2367349904f6630df951b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445995"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="fa78c-102">ISymUnmanagedWriter::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="fa78c-102">ISymUnmanagedWriter::Abort Method</span></span>
<span data-ttu-id="fa78c-103">Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="fa78c-103">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="fa78c-104">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="fa78c-104">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="fa78c-105">Para confirmar los símbolos y cerrar el escritor de símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fa78c-105">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa78c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa78c-106">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fa78c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa78c-107">Return Value</span></span>  
 <span data-ttu-id="fa78c-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="fa78c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa78c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa78c-109">Requirements</span></span>  
 <span data-ttu-id="fa78c-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="fa78c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa78c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa78c-111">See also</span></span>

- [<span data-ttu-id="fa78c-112">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa78c-112">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
