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
ms.openlocfilehash: 53897b6f964afb1f8ca95bc8f93c532e148ad129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730518"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="1f548-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount (Método)</span><span class="sxs-lookup"><span data-stu-id="1f548-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>

<span data-ttu-id="1f548-103">Obtiene el número de documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="1f548-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f548-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f548-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f548-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f548-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="1f548-106">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los documentos.</span><span class="sxs-lookup"><span data-stu-id="1f548-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f548-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1f548-107">Return Value</span></span>  

 <span data-ttu-id="1f548-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1f548-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f548-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f548-109">Requirements</span></span>  

 <span data-ttu-id="1f548-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1f548-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f548-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f548-111">See also</span></span>

- [<span data-ttu-id="1f548-112">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f548-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
