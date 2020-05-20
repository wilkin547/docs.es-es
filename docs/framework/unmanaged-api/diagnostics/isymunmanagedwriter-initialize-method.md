---
title: ISymUnmanagedWriter::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: 1553e616f60b4f05c06b6457d47454dfb4bc2eb7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614778"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="325e8-102">ISymUnmanagedWriter::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="325e8-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="325e8-103">Establece la interfaz emisora de metadatos a la que se asociará este escritor y establece el nombre del archivo de salida en el que se escribirán los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="325e8-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="325e8-104">Este método solo se puede llamar una vez y se debe llamar a este método antes que a cualquier otro método de escritura.</span><span class="sxs-lookup"><span data-stu-id="325e8-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="325e8-105">Algunos escritores pueden requerir un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="325e8-105">Some writers may require a file name.</span></span> <span data-ttu-id="325e8-106">Sin embargo, siempre puede pasar un nombre de archivo a este método sin ningún efecto negativo en escritores que no usen el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="325e8-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325e8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="325e8-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="325e8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="325e8-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="325e8-109">de Puntero a la interfaz de emisor de metadatos.</span><span class="sxs-lookup"><span data-stu-id="325e8-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="325e8-110">de Nombre del archivo en el que se escriben los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="325e8-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="325e8-111">Si se especifica un nombre de archivo para un escritor que no usa nombres de archivo, se omite este parámetro.</span><span class="sxs-lookup"><span data-stu-id="325e8-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="325e8-112">de Si se especifica, el escritor de símbolos emitirá los símbolos en el especificado, en <xref:System.Runtime.InteropServices.ComTypes.IStream> lugar de en el archivo especificado en el `filename` parámetro.</span><span class="sxs-lookup"><span data-stu-id="325e8-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="325e8-113">El `pIStream` es opcional.</span><span class="sxs-lookup"><span data-stu-id="325e8-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="325e8-114">[in] `true` es si se trata de una recompilación completa; `false`es si se trata de una compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="325e8-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="325e8-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="325e8-115">Return Value</span></span>  
 <span data-ttu-id="325e8-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="325e8-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="325e8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="325e8-117">Requirements</span></span>  
 <span data-ttu-id="325e8-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="325e8-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325e8-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="325e8-119">See also</span></span>

- [<span data-ttu-id="325e8-120">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="325e8-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="325e8-121">Método Initialize2</span><span class="sxs-lookup"><span data-stu-id="325e8-121">Initialize2 Method</span></span>](isymunmanagedwriter-initialize2-method.md)
