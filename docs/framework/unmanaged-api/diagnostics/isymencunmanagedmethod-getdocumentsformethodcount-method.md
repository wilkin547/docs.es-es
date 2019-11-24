---
title: ISymENCUnmanagedMethod::GetDocumentsForMethodCount (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
ms.openlocfilehash: 057b901337ded7b5336ef673624d8d6c827c8932
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448676"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="4839c-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount (Método)</span><span class="sxs-lookup"><span data-stu-id="4839c-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="4839c-103">Gets the number of documents that this method has lines in.</span><span class="sxs-lookup"><span data-stu-id="4839c-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4839c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4839c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4839c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4839c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4839c-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span><span class="sxs-lookup"><span data-stu-id="4839c-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4839c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4839c-107">Return Value</span></span>  
 <span data-ttu-id="4839c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="4839c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4839c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4839c-109">Requirements</span></span>  
 <span data-ttu-id="4839c-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4839c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4839c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4839c-111">See also</span></span>

- [<span data-ttu-id="4839c-112">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4839c-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
