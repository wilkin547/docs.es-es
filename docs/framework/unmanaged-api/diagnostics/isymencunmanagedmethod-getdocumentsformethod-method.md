---
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
ms.openlocfilehash: 89be772ee3d8a6fc5acb74d5ebe6d3c691764f89
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441960"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="25028-102">ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="25028-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="25028-103">Obtiene los documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="25028-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25028-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25028-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25028-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25028-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="25028-106">de Longitud del búfer al que apunta `pcDocs` .</span><span class="sxs-lookup"><span data-stu-id="25028-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="25028-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los documentos.</span><span class="sxs-lookup"><span data-stu-id="25028-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="25028-108">de Búfer que contiene los documentos.</span><span class="sxs-lookup"><span data-stu-id="25028-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25028-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25028-109">Return Value</span></span>  
 <span data-ttu-id="25028-110">S_OK si el método se ejecuta correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="25028-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25028-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25028-111">Requirements</span></span>  
 <span data-ttu-id="25028-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="25028-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25028-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="25028-113">See also</span></span>

- [<span data-ttu-id="25028-114">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25028-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
