---
title: ISymUnmanagedDocumentWriter::SetSource (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 06c6f9b05d34ea98dde437393ded289cbab2f61d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615532"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="dc965-102">ISymUnmanagedDocumentWriter::SetSource (Método)</span><span class="sxs-lookup"><span data-stu-id="dc965-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="dc965-103">Establece el origen incrustado de un documento que se está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="dc965-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc965-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc965-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc965-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc965-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="dc965-106">de Un `ULONG32` que contiene el tamaño del `source` búfer.</span><span class="sxs-lookup"><span data-stu-id="dc965-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="dc965-107">de Búfer que almacena el código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="dc965-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc965-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dc965-108">Return Value</span></span>  
 <span data-ttu-id="dc965-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="dc965-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc965-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc965-110">Requirements</span></span>  
 <span data-ttu-id="dc965-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dc965-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc965-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="dc965-112">See also</span></span>

- [<span data-ttu-id="dc965-113">ISymUnmanagedDocumentWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc965-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
