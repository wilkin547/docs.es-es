---
description: 'Más información sobre: ISymUnmanagedDocumentWriter:: SetSource (método)'
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
ms.openlocfilehash: e24e34a297a9931babf3df4f2bae1b5e8f60db1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721481"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="64581-103">ISymUnmanagedDocumentWriter::SetSource (Método)</span><span class="sxs-lookup"><span data-stu-id="64581-103">ISymUnmanagedDocumentWriter::SetSource Method</span></span>

<span data-ttu-id="64581-104">Establece el origen incrustado de un documento que se está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="64581-104">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64581-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64581-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64581-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64581-106">Parameters</span></span>  

 `sourceSize`  
 <span data-ttu-id="64581-107">de Un `ULONG32` que contiene el tamaño del `source` búfer.</span><span class="sxs-lookup"><span data-stu-id="64581-107">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="64581-108">de Búfer que almacena el código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="64581-108">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64581-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64581-109">Return Value</span></span>  

 <span data-ttu-id="64581-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="64581-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64581-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64581-111">Requirements</span></span>  

 <span data-ttu-id="64581-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="64581-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64581-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="64581-113">See also</span></span>

- [<span data-ttu-id="64581-114">ISymUnmanagedDocumentWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64581-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
