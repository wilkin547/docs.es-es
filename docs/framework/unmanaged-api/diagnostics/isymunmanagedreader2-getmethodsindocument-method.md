---
title: ISymUnmanagedReader2::GetMethodsInDocument (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7fa192a8e8b8a876f672e36bb906a714b1266e2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736666"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="46e2f-102">ISymUnmanagedReader2::GetMethodsInDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="46e2f-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="46e2f-103">Obtiene todos los métodos que tiene información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="46e2f-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46e2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46e2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46e2f-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="46e2f-106">[in] Un puntero al documento.</span><span class="sxs-lookup"><span data-stu-id="46e2f-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="46e2f-107">[in] Un `ULONG32` que indica el tamaño de la `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="46e2f-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="46e2f-108">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los métodos.</span><span class="sxs-lookup"><span data-stu-id="46e2f-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="46e2f-109">[out] Un puntero al búfer que recibe los métodos.</span><span class="sxs-lookup"><span data-stu-id="46e2f-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46e2f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="46e2f-110">Return Value</span></span>  
 <span data-ttu-id="46e2f-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="46e2f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46e2f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46e2f-112">Requirements</span></span>  
 <span data-ttu-id="46e2f-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="46e2f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e2f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="46e2f-114">See also</span></span>

- [<span data-ttu-id="46e2f-115">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46e2f-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
