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
ms.openlocfilehash: d4f896dcd78061284416468968ba5a9a5fbbda2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428545"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="9e952-102">ISymUnmanagedBinder::GetReaderForFile (Método)</span><span class="sxs-lookup"><span data-stu-id="9e952-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="9e952-103">A partir de una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> estructura que va a leer los símbolos de depuración asociados al módulo.</span><span class="sxs-lookup"><span data-stu-id="9e952-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="9e952-104">Este método abrirá el archivo de programa (PDB) de la base de datos solo si está junto al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="9e952-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="9e952-105">Este cambio se realizó por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9e952-105">This change has been made for security purposes.</span></span> <span data-ttu-id="9e952-106">Si necesita una búsqueda más extensa para el archivo PDB, utilice la [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="9e952-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e952-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e952-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e952-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e952-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="9e952-109">[in] Un puntero a la interfaz de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9e952-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="9e952-110">[in] Un puntero al nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="9e952-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="9e952-111">[in] Un puntero a la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9e952-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9e952-112">[out] Un puntero que se establece en el valor devuelto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaz.</span><span class="sxs-lookup"><span data-stu-id="9e952-112">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e952-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9e952-113">Return Value</span></span>  
 <span data-ttu-id="9e952-114">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9e952-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e952-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e952-115">Requirements</span></span>  
 <span data-ttu-id="9e952-116">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e952-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e952-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e952-117">See Also</span></span>  
 [<span data-ttu-id="9e952-118">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e952-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="9e952-119">GetReaderForFile2 (método)</span><span class="sxs-lookup"><span data-stu-id="9e952-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
