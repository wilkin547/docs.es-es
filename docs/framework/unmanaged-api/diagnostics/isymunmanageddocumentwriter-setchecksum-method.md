---
title: ISymUnmanagedDocumentWriter::SetCheckSum (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b9b77b94e466a4aab4a575501ac6922293b3410
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424149"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="197fd-102">ISymUnmanagedDocumentWriter::SetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="197fd-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="197fd-103">Establece la información de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="197fd-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="197fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="197fd-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="197fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="197fd-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="197fd-106">[in] El GUID que representa el identificador del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="197fd-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="197fd-107">[in] A `ULONG32` que indica el tamaño, en bytes, de la `checkSum` búfer.</span><span class="sxs-lookup"><span data-stu-id="197fd-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="197fd-108">[in] El búfer que almacena la información de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="197fd-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="197fd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="197fd-109">Return Value</span></span>  
 <span data-ttu-id="197fd-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="197fd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="197fd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="197fd-111">Requirements</span></span>  
 <span data-ttu-id="197fd-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="197fd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="197fd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="197fd-113">See Also</span></span>  
 [<span data-ttu-id="197fd-114">ISymUnmanagedDocumentWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="197fd-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
