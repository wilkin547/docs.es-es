---
title: "ISymUnmanagedWriter::Initialize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bae368919941e6a0b234736f789320b62405a17b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="485c6-102">ISymUnmanagedWriter::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="485c6-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="485c6-103">Establece la interfaz emisora de metadatos con el que se asociará este sistema de escritura y el nombre de archivo de salida a la que se escribirán los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="485c6-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="485c6-104">Puede llamar a este método solo una vez y debe llamarse antes de cualquier otro método de escritura.</span><span class="sxs-lookup"><span data-stu-id="485c6-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="485c6-105">Algunos escritores pueden requerir un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="485c6-105">Some writers may require a file name.</span></span> <span data-ttu-id="485c6-106">Sin embargo, siempre se puede pasar un nombre de archivo a este método sin ningún efecto negativo en escritura que no utilicen el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="485c6-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="485c6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="485c6-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="485c6-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="485c6-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="485c6-109">[in] Un puntero a interfaz emisora de metadatos.</span><span class="sxs-lookup"><span data-stu-id="485c6-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="485c6-110">[in] El nombre de archivo a la que se escriben los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="485c6-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="485c6-111">Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="485c6-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="485c6-112">[in] Si se especifica, el escritor de símbolos emitirá los símbolos en el dado <xref:System.Runtime.InteropServices.ComTypes.IStream> en vez de en el archivo especificado en el `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="485c6-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="485c6-113">El parámetro `pIStream` es opcional.</span><span class="sxs-lookup"><span data-stu-id="485c6-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="485c6-114">[in] `true` si se trata de una regeneración completa; `false` si se trata de una compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="485c6-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="485c6-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="485c6-115">Return Value</span></span>  
 <span data-ttu-id="485c6-116">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="485c6-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="485c6-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="485c6-117">Requirements</span></span>  
 <span data-ttu-id="485c6-118">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="485c6-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="485c6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="485c6-119">See Also</span></span>  
 [<span data-ttu-id="485c6-120">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="485c6-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="485c6-121">Initialize2 (método)</span><span class="sxs-lookup"><span data-stu-id="485c6-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
