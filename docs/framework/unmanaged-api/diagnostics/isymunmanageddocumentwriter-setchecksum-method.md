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
ms.openlocfilehash: dbf876a514ce106c566a168f688eb3a22d3a1ea2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449047"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="680e6-102">ISymUnmanagedDocumentWriter::SetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="680e6-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="680e6-103">Establece la información de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="680e6-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="680e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="680e6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="680e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="680e6-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="680e6-106">de GUID que representa el identificador del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="680e6-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="680e6-107">de `ULONG32` que indica el tamaño, en bytes, del búfer de `checkSum`.</span><span class="sxs-lookup"><span data-stu-id="680e6-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="680e6-108">de Búfer que almacena la información de la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="680e6-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="680e6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="680e6-109">Return Value</span></span>  
 <span data-ttu-id="680e6-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="680e6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="680e6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="680e6-111">Requirements</span></span>  
 <span data-ttu-id="680e6-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="680e6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680e6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="680e6-113">See also</span></span>

- [<span data-ttu-id="680e6-114">ISymUnmanagedDocumentWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="680e6-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
