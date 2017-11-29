---
title: "ISymUnmanagedReader2::GetMethodsInDocument (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetMethodsInDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 15053aeb3febd533a6977ef446fc1aa3bd8a92b8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="1d655-102">ISymUnmanagedReader2::GetMethodsInDocument (Método)</span><span class="sxs-lookup"><span data-stu-id="1d655-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="1d655-103">Obtiene cada método que tiene información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="1d655-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d655-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d655-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d655-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d655-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="1d655-106">[in] Un puntero al documento.</span><span class="sxs-lookup"><span data-stu-id="1d655-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="1d655-107">[in] A `ULONG32` que indica el tamaño de la `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="1d655-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="1d655-108">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los métodos.</span><span class="sxs-lookup"><span data-stu-id="1d655-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1d655-109">[out] Un puntero al búfer que recibe los métodos.</span><span class="sxs-lookup"><span data-stu-id="1d655-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d655-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1d655-110">Return Value</span></span>  
 <span data-ttu-id="1d655-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1d655-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d655-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d655-112">Requirements</span></span>  
 <span data-ttu-id="1d655-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1d655-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d655-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d655-114">See Also</span></span>  
 [<span data-ttu-id="1d655-115">ISymUnmanagedReader2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d655-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
