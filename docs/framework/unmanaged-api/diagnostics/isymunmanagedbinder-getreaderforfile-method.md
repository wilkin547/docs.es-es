---
title: ISymUnmanagedBinder::GetReaderForFile (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6081e2dfd64625697295f2ea2d1560bc597838da
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776859"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="baec3-102">ISymUnmanagedBinder::GetReaderForFile (Método)</span><span class="sxs-lookup"><span data-stu-id="baec3-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="baec3-103">Dada una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaz que va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="baec3-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="baec3-104">Este método abrirá el archivo de programa (PDB) de la base de datos solo si está junto al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="baec3-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="baec3-105">Este cambio se realizó por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="baec3-105">This change has been made for security purposes.</span></span> <span data-ttu-id="baec3-106">Si necesita una búsqueda más extensa para el archivo PDB, utilice el [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="baec3-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baec3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="baec3-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baec3-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="baec3-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="baec3-109">[in] Un puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="baec3-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="baec3-110">[in] Un puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="baec3-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="baec3-111">[in] Un puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="baec3-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="baec3-112">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="baec3-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="baec3-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="baec3-113">Return Value</span></span>  
 <span data-ttu-id="baec3-114">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="baec3-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baec3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="baec3-115">Requirements</span></span>  
 <span data-ttu-id="baec3-116">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="baec3-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baec3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="baec3-117">See also</span></span>

- [<span data-ttu-id="baec3-118">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="baec3-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="baec3-119">GetReaderForFile2 (método)</span><span class="sxs-lookup"><span data-stu-id="baec3-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
