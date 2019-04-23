---
title: ISymUnmanagedReader::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 661c27b9c21f77104b8a86163d3c92d44f8a85df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181784"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="c4151-102">ISymUnmanagedReader::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="c4151-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="c4151-103">Inicializa el lector de símbolos con la interfaz de importador de metadatos que se asociará con, junto con el nombre de archivo del módulo de este lector.</span><span class="sxs-lookup"><span data-stu-id="c4151-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4151-104">Este método puede llamar a una sola vez y debe llamarse antes que cualquier otro método de lector.</span><span class="sxs-lookup"><span data-stu-id="c4151-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4151-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4151-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4151-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4151-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="c4151-107">[in] La interfaz de importador de metadatos con el que se asociará este lector.</span><span class="sxs-lookup"><span data-stu-id="c4151-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="c4151-108">[in] El nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="c4151-108">[in] The file name of the module.</span></span> <span data-ttu-id="c4151-109">Puede usar el `pIStream` parámetro en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c4151-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="c4151-110">[in] La ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c4151-110">[in] The path to search.</span></span> <span data-ttu-id="c4151-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="c4151-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="c4151-112">[in] La secuencia de archivos, usar como alternativa al parámetro filename.</span><span class="sxs-lookup"><span data-stu-id="c4151-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4151-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c4151-113">Return Value</span></span>  
 <span data-ttu-id="c4151-114">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c4151-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4151-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4151-115">Remarks</span></span>  
 <span data-ttu-id="c4151-116">Debe especificar solo uno de los `filename` o `pIStream` parámetros, no ambos.</span><span class="sxs-lookup"><span data-stu-id="c4151-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="c4151-117">El parámetro `searchPath` es opcional.</span><span class="sxs-lookup"><span data-stu-id="c4151-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4151-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4151-118">Requirements</span></span>  
 <span data-ttu-id="c4151-119">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c4151-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4151-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4151-120">See also</span></span>

- [<span data-ttu-id="c4151-121">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4151-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
