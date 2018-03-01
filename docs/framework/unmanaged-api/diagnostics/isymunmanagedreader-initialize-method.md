---
title: "ISymUnmanagedReader::Initialize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 433cd62f7801d386f3b34b7fc8e95bd1d0c5f765
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="9a7e7-102">ISymUnmanagedReader::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="9a7e7-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="9a7e7-103">Inicializa el lector de símbolos con la interfaz de importador de metadatos que este lector estarán asociado a, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a7e7-104">Este método puede llamar una sola vez y debe llamarse antes que cualquier otro método de lector.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a7e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a7e7-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a7e7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a7e7-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="9a7e7-107">[in] La interfaz de importador de metadatos con el que se asociará este lector.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="9a7e7-108">[in] El nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-108">[in] The file name of the module.</span></span> <span data-ttu-id="9a7e7-109">Puede usar el `pIStream` parámetro en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="9a7e7-110">[in] La ruta de acceso para buscar.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-110">[in] The path to search.</span></span> <span data-ttu-id="9a7e7-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="9a7e7-112">[in] Secuencia de archivo, que se utiliza como alternativa al parámetro filename.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a7e7-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a7e7-113">Return Value</span></span>  
 <span data-ttu-id="9a7e7-114">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a7e7-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a7e7-115">Remarks</span></span>  
 <span data-ttu-id="9a7e7-116">Debe especificar sólo uno de los `filename` o `pIStream` parámetros, no ambos.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="9a7e7-117">El parámetro `searchPath` es opcional.</span><span class="sxs-lookup"><span data-stu-id="9a7e7-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a7e7-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a7e7-118">Requirements</span></span>  
 <span data-ttu-id="9a7e7-119">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a7e7-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a7e7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a7e7-120">See Also</span></span>  
 [<span data-ttu-id="9a7e7-121">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a7e7-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
