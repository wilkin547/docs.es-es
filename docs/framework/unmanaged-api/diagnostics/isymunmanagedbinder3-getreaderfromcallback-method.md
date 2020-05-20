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
ms.openlocfilehash: 4a23e9aa259f430c0d0579657952fc6aba4c307c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441661"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="f4abb-102">ISymUnmanagedBinder3::GetReaderFromCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="f4abb-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="f4abb-103">Permite al usuario implementar o proporcionar a través `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` de la devolución de llamada o para obtener la información del directorio de depuración de la memoria.</span><span class="sxs-lookup"><span data-stu-id="f4abb-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4abb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4abb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4abb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4abb-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="f4abb-106">de Puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f4abb-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="f4abb-107">de Puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="f4abb-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="f4abb-108">de Puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f4abb-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="f4abb-109">de Un valor de la enumeración [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md) que especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f4abb-109">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="f4abb-110">de Puntero a la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f4abb-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f4abb-111">enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="f4abb-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4abb-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f4abb-112">Return Value</span></span>  
 <span data-ttu-id="f4abb-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f4abb-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4abb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4abb-114">Requirements</span></span>  
 <span data-ttu-id="f4abb-115">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="f4abb-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4abb-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="f4abb-116">See also</span></span>

- [<span data-ttu-id="f4abb-117">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4abb-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
