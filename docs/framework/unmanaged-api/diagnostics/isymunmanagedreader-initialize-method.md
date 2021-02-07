---
description: 'Más información acerca de: ISymUnmanagedReader:: Initialize (método)'
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
ms.openlocfilehash: cf7f5df3efed7823fc36bd6c9fc56e0c49d17443
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763883"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="8909a-103">ISymUnmanagedReader::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="8909a-103">ISymUnmanagedReader::Initialize Method</span></span>

<span data-ttu-id="8909a-104">Inicializa el lector de símbolos con la interfaz de importador de metadatos a la que se asociará este lector, junto con el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="8909a-104">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8909a-105">Este método solo se puede llamar una vez y se debe llamar a antes que a cualquier otro método de lectura.</span><span class="sxs-lookup"><span data-stu-id="8909a-105">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8909a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8909a-106">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8909a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8909a-107">Parameters</span></span>  

 `importer`  
 <span data-ttu-id="8909a-108">de La interfaz de importador de metadatos a la que se asociará este lector.</span><span class="sxs-lookup"><span data-stu-id="8909a-108">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="8909a-109">de Nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="8909a-109">[in] The file name of the module.</span></span> <span data-ttu-id="8909a-110">En su lugar, puede usar el `pIStream` parámetro.</span><span class="sxs-lookup"><span data-stu-id="8909a-110">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="8909a-111">de Ruta de acceso que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="8909a-111">[in] The path to search.</span></span> <span data-ttu-id="8909a-112">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="8909a-112">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="8909a-113">de El flujo de archivo, que se usa como alternativa al parámetro FILENAME.</span><span class="sxs-lookup"><span data-stu-id="8909a-113">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8909a-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8909a-114">Return Value</span></span>  

 <span data-ttu-id="8909a-115">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8909a-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8909a-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8909a-116">Remarks</span></span>  

 <span data-ttu-id="8909a-117">Solo tiene que especificar uno de los `filename` `pIStream` parámetros o, no ambos.</span><span class="sxs-lookup"><span data-stu-id="8909a-117">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="8909a-118">El `searchPath` es opcional.</span><span class="sxs-lookup"><span data-stu-id="8909a-118">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8909a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8909a-119">Requirements</span></span>  

 <span data-ttu-id="8909a-120">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8909a-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8909a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8909a-121">See also</span></span>

- [<span data-ttu-id="8909a-122">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8909a-122">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
