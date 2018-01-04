---
title: "ISymUnmanagedBinder2::GetReaderForFile2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2.GetReaderForFile2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 270a154c40b85ad4774bececf12685393f4d6c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="7aba3-102">ISymUnmanagedBinder2::GetReaderForFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="7aba3-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="7aba3-103">A partir de una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaz que se va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="7aba3-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="7aba3-104">Este método proporciona una búsqueda más extensa para el archivo de programa (PDB) de la base de datos que la [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="7aba3-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aba3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7aba3-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7aba3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7aba3-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="7aba3-107">[in] Un puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7aba3-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="7aba3-108">[in] Un puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="7aba3-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="7aba3-109">[in] Un puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7aba3-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="7aba3-110">[in] Un valor de la [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeración que especifica la directiva que se utilizará al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7aba3-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7aba3-111">[out] Un puntero que se establece en el valor devuelto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaz.</span><span class="sxs-lookup"><span data-stu-id="7aba3-111">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7aba3-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7aba3-112">Return Value</span></span>  
 <span data-ttu-id="7aba3-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7aba3-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aba3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7aba3-114">Requirements</span></span>  
 <span data-ttu-id="7aba3-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7aba3-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7aba3-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7aba3-116">Remarks</span></span>  
 <span data-ttu-id="7aba3-117">Esta versión del método puede buscar el archivo PDB en áreas distintas situada junto al módulo.</span><span class="sxs-lookup"><span data-stu-id="7aba3-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="7aba3-118">La directiva de búsqueda puede controlarse mediante la combinación [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="7aba3-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="7aba3-119">Por ejemplo, `AllowReferencePathAccess | AllowSymbolServerAccess` busca el archivo PDB junto al archivo ejecutable y en un servidor de símbolos, pero no consultar el registro o use la ruta de acceso en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="7aba3-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="7aba3-120">Si el `searchPath` se proporciona el parámetro, se buscará en esos directorios.</span><span class="sxs-lookup"><span data-stu-id="7aba3-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aba3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7aba3-121">See Also</span></span>  
 [<span data-ttu-id="7aba3-122">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7aba3-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="7aba3-123">GetReaderForFile (método)</span><span class="sxs-lookup"><span data-stu-id="7aba3-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
