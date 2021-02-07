---
description: 'Más información acerca de: ISymUnmanagedWriter:: ABORT (método)'
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
ms.openlocfilehash: 312694bf2b667ea78bf5ddc993d0e2b71c85a8ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762687"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="3ba60-103">ISymUnmanagedWriter::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="3ba60-103">ISymUnmanagedWriter::Abort Method</span></span>

<span data-ttu-id="3ba60-104">Cierra el escritor de símbolos sin confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3ba60-104">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="3ba60-105">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="3ba60-105">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="3ba60-106">Para confirmar los símbolos y cerrar el escritor de símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: Close](isymunmanagedwriter-close-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3ba60-106">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ba60-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ba60-107">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3ba60-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ba60-108">Return Value</span></span>  

 <span data-ttu-id="3ba60-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3ba60-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ba60-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ba60-110">Requirements</span></span>  

 <span data-ttu-id="3ba60-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3ba60-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba60-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ba60-112">See also</span></span>

- [<span data-ttu-id="3ba60-113">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ba60-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
