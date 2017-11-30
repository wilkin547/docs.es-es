---
title: "ISymUnmanagedBinder::GetReaderFromStream (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderFromStream
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aa6a2e60e34f6c3a78343318ae102883da84e266
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="7f172-102">ISymUnmanagedBinder::GetReaderFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="7f172-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="7f172-103">A partir de una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) símbolos estructura que va a leer la depuración desde el almacén de símbolos especificado.</span><span class="sxs-lookup"><span data-stu-id="7f172-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f172-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f172-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f172-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f172-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="7f172-106">[in] Un puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7f172-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="7f172-107">[in] Un puntero a la secuencia que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7f172-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7f172-108">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="7f172-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f172-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7f172-109">Return Value</span></span>  
 <span data-ttu-id="7f172-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7f172-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f172-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f172-111">Requirements</span></span>  
 <span data-ttu-id="7f172-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7f172-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f172-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f172-113">See Also</span></span>  
 [<span data-ttu-id="7f172-114">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f172-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
