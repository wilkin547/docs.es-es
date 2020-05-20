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
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615480"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="528f5-102">ISymUnmanagedReader::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="528f5-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="528f5-103">Inicializa el lector de símbolos con la interfaz de importador de metadatos a la que se asociará este lector, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="528f5-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="528f5-104">Este método solo se puede llamar una vez y se debe llamar a antes que a cualquier otro método de lectura.</span><span class="sxs-lookup"><span data-stu-id="528f5-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="528f5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="528f5-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="528f5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="528f5-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="528f5-107">de La interfaz de importador de metadatos a la que se asociará este lector.</span><span class="sxs-lookup"><span data-stu-id="528f5-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="528f5-108">de Nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="528f5-108">[in] The file name of the module.</span></span> <span data-ttu-id="528f5-109">En su lugar, puede usar el `pIStream` parámetro.</span><span class="sxs-lookup"><span data-stu-id="528f5-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="528f5-110">de Ruta de acceso que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="528f5-110">[in] The path to search.</span></span> <span data-ttu-id="528f5-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="528f5-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="528f5-112">de El flujo de archivo, que se usa como alternativa al parámetro FILENAME.</span><span class="sxs-lookup"><span data-stu-id="528f5-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="528f5-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="528f5-113">Return Value</span></span>  
 <span data-ttu-id="528f5-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="528f5-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="528f5-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="528f5-115">Remarks</span></span>  
 <span data-ttu-id="528f5-116">Solo tiene que especificar uno de los `filename` `pIStream` parámetros o, no ambos.</span><span class="sxs-lookup"><span data-stu-id="528f5-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="528f5-117">El `searchPath` es opcional.</span><span class="sxs-lookup"><span data-stu-id="528f5-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="528f5-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="528f5-118">Requirements</span></span>  
 <span data-ttu-id="528f5-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="528f5-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528f5-120">Consulta también</span><span class="sxs-lookup"><span data-stu-id="528f5-120">See also</span></span>

- [<span data-ttu-id="528f5-121">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="528f5-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
