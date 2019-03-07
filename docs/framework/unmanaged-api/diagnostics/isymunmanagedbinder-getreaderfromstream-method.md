---
title: ISymUnmanagedBinder::GetReaderFromStream (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 630895e131c2b3fd5a175a7a3c45140ad65d03aa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503039"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="3db0e-102">ISymUnmanagedBinder::GetReaderFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="3db0e-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="3db0e-103">Dada una interfaz de metadatos y una secuencia que contiene el almacén de símbolos, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) estructura que leerá la depuración de símbolos desde el almacén de símbolos especificado.</span><span class="sxs-lookup"><span data-stu-id="3db0e-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db0e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3db0e-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3db0e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3db0e-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="3db0e-106">[in] Un puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3db0e-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="3db0e-107">[in] Un puntero a la secuencia que contiene el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="3db0e-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3db0e-108">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="3db0e-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3db0e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3db0e-109">Return Value</span></span>  
 <span data-ttu-id="3db0e-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3db0e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3db0e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3db0e-111">Requirements</span></span>  
 <span data-ttu-id="3db0e-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3db0e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db0e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3db0e-113">See also</span></span>
- [<span data-ttu-id="3db0e-114">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3db0e-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
