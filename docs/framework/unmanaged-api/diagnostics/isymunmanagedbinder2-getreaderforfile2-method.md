---
title: ISymUnmanagedBinder2::GetReaderForFile2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db917820de92b2e347385afc5217c0ca190825cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776836"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="7e4fa-102">ISymUnmanagedBinder2::GetReaderForFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="7e4fa-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="7e4fa-103">Dada una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaz que va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="7e4fa-104">Este método proporciona una búsqueda más extensa para el archivo de programa (PDB) de la base de datos que el [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e4fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e4fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e4fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e4fa-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="7e4fa-107">[in] Un puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="7e4fa-108">[in] Un puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="7e4fa-109">[in] Un puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="7e4fa-110">[in] Un valor de la [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeración que especifica la directiva que se usará al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7e4fa-111">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e4fa-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e4fa-112">Return Value</span></span>  
 <span data-ttu-id="7e4fa-113">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e4fa-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e4fa-114">Requirements</span></span>  
 <span data-ttu-id="7e4fa-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e4fa-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e4fa-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e4fa-116">Remarks</span></span>  
 <span data-ttu-id="7e4fa-117">Puede buscar el archivo PDB en áreas distintas derecha junto al módulo de esta versión del método.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="7e4fa-118">La directiva de búsqueda puede controlarse mediante la combinación [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="7e4fa-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="7e4fa-119">Por ejemplo, `AllowReferencePathAccess | AllowSymbolServerAccess` busca el archivo PDB junto al archivo ejecutable y en un servidor de símbolos, pero no consultar el registro o use la ruta de acceso en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="7e4fa-120">Si el `searchPath` parámetro se proporciona, se buscará en esos directorios.</span><span class="sxs-lookup"><span data-stu-id="7e4fa-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4fa-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e4fa-121">See also</span></span>

- [<span data-ttu-id="7e4fa-122">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e4fa-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="7e4fa-123">GetReaderForFile (método)</span><span class="sxs-lookup"><span data-stu-id="7e4fa-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
