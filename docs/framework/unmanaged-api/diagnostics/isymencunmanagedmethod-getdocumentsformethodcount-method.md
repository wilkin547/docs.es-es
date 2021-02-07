---
description: 'Más información sobre: ISymENCUnmanagedMethod:: GetDocumentsForMethodCount ((método)'
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
ms.openlocfilehash: 0594771c544ad1de32531e92f30fe96f245b5699
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738018"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="add49-103">ISymENCUnmanagedMethod::GetDocumentsForMethodCount (Método)</span><span class="sxs-lookup"><span data-stu-id="add49-103">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>

<span data-ttu-id="add49-104">Obtiene el número de documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="add49-104">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="add49-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="add49-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="add49-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="add49-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="add49-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los documentos.</span><span class="sxs-lookup"><span data-stu-id="add49-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="add49-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="add49-108">Return Value</span></span>  

 <span data-ttu-id="add49-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="add49-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="add49-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="add49-110">Requirements</span></span>  

 <span data-ttu-id="add49-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="add49-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="add49-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="add49-112">See also</span></span>

- [<span data-ttu-id="add49-113">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="add49-113">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
