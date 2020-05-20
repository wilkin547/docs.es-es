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
ms.openlocfilehash: 06a331e24622e0a155d974ca869818a6532baa1f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615545"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="8f1fe-102">ISymUnmanagedDocumentWriter::SetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="8f1fe-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="8f1fe-103">Establece la información de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8f1fe-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f1fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f1fe-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f1fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f1fe-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="8f1fe-106">de GUID que representa el identificador del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="8f1fe-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="8f1fe-107">de `ULONG32`Que indica el tamaño, en bytes, del `checkSum` búfer.</span><span class="sxs-lookup"><span data-stu-id="8f1fe-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="8f1fe-108">de Búfer que almacena la información de la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8f1fe-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f1fe-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8f1fe-109">Return Value</span></span>  
 <span data-ttu-id="8f1fe-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8f1fe-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f1fe-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f1fe-111">Requirements</span></span>  
 <span data-ttu-id="8f1fe-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8f1fe-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1fe-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="8f1fe-113">See also</span></span>

- [<span data-ttu-id="8f1fe-114">ISymUnmanagedDocumentWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f1fe-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
