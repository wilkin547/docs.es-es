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
ms.openlocfilehash: ca34d1d84d6f9960d021c35566f8412df321464d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429737"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="233fc-102">ISymUnmanagedReader::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="233fc-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="233fc-103">Inicializa el lector de símbolos con la interfaz de importador de metadatos a la que se asociará este lector, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="233fc-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="233fc-104">Este método solo se puede llamar una vez y se debe llamar a antes que a cualquier otro método de lectura.</span><span class="sxs-lookup"><span data-stu-id="233fc-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="233fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="233fc-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="233fc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="233fc-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="233fc-107">de La interfaz de importador de metadatos a la que se asociará este lector.</span><span class="sxs-lookup"><span data-stu-id="233fc-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="233fc-108">de Nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="233fc-108">[in] The file name of the module.</span></span> <span data-ttu-id="233fc-109">En su lugar, puede usar el parámetro `pIStream`.</span><span class="sxs-lookup"><span data-stu-id="233fc-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="233fc-110">de Ruta de acceso que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="233fc-110">[in] The path to search.</span></span> <span data-ttu-id="233fc-111">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="233fc-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="233fc-112">de El flujo de archivo, que se usa como alternativa al parámetro FILENAME.</span><span class="sxs-lookup"><span data-stu-id="233fc-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="233fc-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="233fc-113">Return Value</span></span>  
 <span data-ttu-id="233fc-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="233fc-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="233fc-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="233fc-115">Remarks</span></span>  
 <span data-ttu-id="233fc-116">Solo tiene que especificar uno de los parámetros `filename` o `pIStream`, no ambos.</span><span class="sxs-lookup"><span data-stu-id="233fc-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="233fc-117">El parámetro `searchPath` es opcional.</span><span class="sxs-lookup"><span data-stu-id="233fc-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="233fc-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="233fc-118">Requirements</span></span>  
 <span data-ttu-id="233fc-119">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="233fc-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="233fc-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="233fc-120">See also</span></span>

- [<span data-ttu-id="233fc-121">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="233fc-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
