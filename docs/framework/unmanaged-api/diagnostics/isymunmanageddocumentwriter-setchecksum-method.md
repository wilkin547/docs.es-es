---
description: 'Más información sobre: ISymUnmanagedDocumentWriter:: Setchecksum ((método)'
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
ms.openlocfilehash: ac2ba9654f3610dca333cf0e06c20696cf31bd1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710093"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="8e4e5-103">ISymUnmanagedDocumentWriter::SetCheckSum (Método)</span><span class="sxs-lookup"><span data-stu-id="8e4e5-103">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>

<span data-ttu-id="8e4e5-104">Establece la información de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-104">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e4e5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e4e5-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e4e5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e4e5-106">Parameters</span></span>  

 `algorithmId`  
 <span data-ttu-id="8e4e5-107">de GUID que representa el identificador del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-107">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="8e4e5-108">de `ULONG32` Que indica el tamaño, en bytes, del `checkSum` búfer.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-108">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="8e4e5-109">de Búfer que almacena la información de la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-109">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e4e5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e4e5-110">Return Value</span></span>  

 <span data-ttu-id="8e4e5-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e4e5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e4e5-112">Requirements</span></span>  

 <span data-ttu-id="8e4e5-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8e4e5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e4e5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e4e5-114">See also</span></span>

- [<span data-ttu-id="8e4e5-115">ISymUnmanagedDocumentWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e4e5-115">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
