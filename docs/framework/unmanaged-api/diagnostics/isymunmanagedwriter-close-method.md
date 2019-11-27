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
ms.openlocfilehash: cd601ac6041ca22d59d7467bafc7c1d87b21371f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428114"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="c5bd1-102">ISymUnmanagedWriter::Close (Método)</span><span class="sxs-lookup"><span data-stu-id="c5bd1-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="c5bd1-103">Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c5bd1-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bd1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5bd1-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c5bd1-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c5bd1-105">Return Value</span></span>  
 <span data-ttu-id="c5bd1-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c5bd1-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5bd1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5bd1-107">Remarks</span></span>  
 <span data-ttu-id="c5bd1-108">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="c5bd1-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="c5bd1-109">Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: ABORT](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c5bd1-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5bd1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5bd1-110">Requirements</span></span>  
 <span data-ttu-id="c5bd1-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c5bd1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bd1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5bd1-112">See also</span></span>

- [<span data-ttu-id="c5bd1-113">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5bd1-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
