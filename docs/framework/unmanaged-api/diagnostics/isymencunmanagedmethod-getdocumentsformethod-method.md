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
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176635"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="114bf-102">ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="114bf-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="114bf-103">Obtiene los documentos en los que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="114bf-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="114bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="114bf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="114bf-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="114bf-106">[en] La longitud del búfer `pcDocs`a la que apunta .</span><span class="sxs-lookup"><span data-stu-id="114bf-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="114bf-107">[fuera] Puntero a `ULONG32` un que recibe el tamaño, en caracteres, del búfer necesario para contener los documentos.</span><span class="sxs-lookup"><span data-stu-id="114bf-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="114bf-108">[en] El búfer que contiene los documentos.</span><span class="sxs-lookup"><span data-stu-id="114bf-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="114bf-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="114bf-109">Return Value</span></span>  
 <span data-ttu-id="114bf-110">S_OK si el método se realiza correctamente; de lo contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="114bf-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="114bf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="114bf-111">Requirements</span></span>  
 <span data-ttu-id="114bf-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="114bf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114bf-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="114bf-113">See also</span></span>

- [<span data-ttu-id="114bf-114">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="114bf-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
