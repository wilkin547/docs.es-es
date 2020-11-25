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
ms.openlocfilehash: 1d684c14f14fcc93040798ae4ee3b8bb1df5354d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733261"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="9babe-102">ISymUnmanagedWriter::Close (Método)</span><span class="sxs-lookup"><span data-stu-id="9babe-102">ISymUnmanagedWriter::Close Method</span></span>

<span data-ttu-id="9babe-103">Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9babe-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9babe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9babe-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9babe-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9babe-105">Return Value</span></span>  

 <span data-ttu-id="9babe-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9babe-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9babe-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9babe-107">Remarks</span></span>  

 <span data-ttu-id="9babe-108">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="9babe-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="9babe-109">Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: ABORT](isymunmanagedwriter-abort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9babe-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9babe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9babe-110">Requirements</span></span>  

 <span data-ttu-id="9babe-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9babe-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9babe-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9babe-112">See also</span></span>

- [<span data-ttu-id="9babe-113">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9babe-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
