---
title: "ISymUnmanagedWriter::Initialize2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e76543c35a717b95ae37985648986abaf16bf85d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="3ff06-102">ISymUnmanagedWriter::Initialize2 (Método)</span><span class="sxs-lookup"><span data-stu-id="3ff06-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="3ff06-103">Establece la interfaz emisora de metadatos con el que se asociará este sistema de escritura y el nombre de archivo de salida a la que se escribirán los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="3ff06-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="3ff06-104">Este método también permite establecer la ubicación final del archivo de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3ff06-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff06-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ff06-105">Syntax</span></span>  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ff06-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ff06-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="3ff06-107">[in] Un puntero a interfaz emisora de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3ff06-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="3ff06-108">[in] Un puntero a un `WCHAR` que contiene el nombre de archivo a la que se escriben los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="3ff06-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="3ff06-109">Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="3ff06-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="3ff06-110">[in] Si se especifica, el escritor de símbolos emite los símbolos en el dado <xref:System.Runtime.InteropServices.ComTypes.IStream> en vez de en el archivo especificado en el `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="3ff06-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="3ff06-111">El parámetro `pIStream` es opcional.</span><span class="sxs-lookup"><span data-stu-id="3ff06-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="3ff06-112">[in] `true` si se trata de una regeneración completa; `false` si se trata de una compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="3ff06-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="3ff06-113">[in] Un puntero a un `WCHAR` que es la cadena de ruta de acceso a la ubicación final del archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="3ff06-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ff06-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ff06-114">Return Value</span></span>  
 <span data-ttu-id="3ff06-115">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3ff06-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ff06-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ff06-116">Requirements</span></span>  
 <span data-ttu-id="3ff06-117">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ff06-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff06-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ff06-118">See Also</span></span>  
 [<span data-ttu-id="3ff06-119">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ff06-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="3ff06-120">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="3ff06-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
