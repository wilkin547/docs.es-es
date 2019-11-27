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
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449302"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="1e16d-102">ISymUnmanagedBinder3::GetReaderFromCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="1e16d-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="1e16d-103">Permite al usuario implementar o proporcionar a través de una devolución de llamada, o bien un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` para obtener la información del directorio de depuración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="1e16d-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e16d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e16d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e16d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e16d-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="1e16d-106">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="1e16d-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="1e16d-107">de Puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="1e16d-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="1e16d-108">de Puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1e16d-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="1e16d-109">de Un valor de la enumeración [corsymsearchpolicyattributes (](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) que especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="1e16d-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="1e16d-110">de Puntero a la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1e16d-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1e16d-111">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="1e16d-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e16d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e16d-112">Return Value</span></span>  
 <span data-ttu-id="1e16d-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1e16d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e16d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e16d-114">Requirements</span></span>  
 <span data-ttu-id="1e16d-115">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="1e16d-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e16d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e16d-116">See also</span></span>

- [<span data-ttu-id="1e16d-117">ISymUnmanagedBinder3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e16d-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
