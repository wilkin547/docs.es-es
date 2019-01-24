---
title: ISymUnmanagedBinder3::GetReaderFromCallback (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5767b60fa992b49fdc2a60feb243a26c0e2ea1ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534558"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="11450-102">ISymUnmanagedBinder3::GetReaderFromCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="11450-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="11450-103">Permite al usuario implementar o proporcionar a través de la devolución de llamada, ya sea un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` para obtener la información de directorio de depuración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="11450-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11450-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11450-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11450-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11450-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="11450-106">[in] Un puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="11450-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="11450-107">[in] Un puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="11450-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="11450-108">[in] Un puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="11450-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="11450-109">[in] Un valor de la [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeración que especifica la directiva que se usará al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="11450-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="11450-110">[in] Un puntero a la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="11450-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="11450-111">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="11450-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11450-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11450-112">Return Value</span></span>  
 <span data-ttu-id="11450-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="11450-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11450-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11450-114">Requirements</span></span>  
 <span data-ttu-id="11450-115">**Encabezado**: CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="11450-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11450-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="11450-116">See also</span></span>
- [<span data-ttu-id="11450-117">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11450-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
