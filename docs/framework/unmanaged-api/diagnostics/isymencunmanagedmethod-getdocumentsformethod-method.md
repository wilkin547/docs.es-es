---
description: 'Más información sobre: ISymENCUnmanagedMethod:: GetDocumentsForMethod ((método)'
title: ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 01c7280abe437266618d96c6e195e61a4f830131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721546"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="c3b63-103">ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="c3b63-103">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>

<span data-ttu-id="c3b63-104">Obtiene los documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="c3b63-104">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b63-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3b63-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b63-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3b63-106">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="c3b63-107">de Longitud del búfer al que apunta `pcDocs` .</span><span class="sxs-lookup"><span data-stu-id="c3b63-107">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="c3b63-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los documentos.</span><span class="sxs-lookup"><span data-stu-id="c3b63-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="c3b63-109">de Búfer que contiene los documentos.</span><span class="sxs-lookup"><span data-stu-id="c3b63-109">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3b63-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3b63-110">Return Value</span></span>  

 <span data-ttu-id="c3b63-111">S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="c3b63-111">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b63-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3b63-112">Requirements</span></span>  

 <span data-ttu-id="c3b63-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c3b63-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b63-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3b63-114">See also</span></span>

- [<span data-ttu-id="c3b63-115">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3b63-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
