---
title: AddFile2 (Método)
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777519"
---
# <a name="addfile2-method"></a><span data-ttu-id="dbe50-102">AddFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="dbe50-102">AddFile2 Method</span></span>
<span data-ttu-id="dbe50-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dbe50-103">Adds files to the assembly.</span></span> <span data-ttu-id="dbe50-104">También se puede usar para crear módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="dbe50-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe50-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbe50-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbe50-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dbe50-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="dbe50-107">IDENTIFICADOR del ensamblado al que se agrega el archivo.</span><span class="sxs-lookup"><span data-stu-id="dbe50-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="dbe50-108">Nombre del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="dbe50-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dbe50-109">Marcas `FileDef` com+ `ffContainsNoMetaData` como y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="dbe50-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="dbe50-110">`dwFlags`se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbe50-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="dbe50-111">Interfaz para la interfaz de [interfaz IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dbe50-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="dbe50-112">Recibe el identificador del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="dbe50-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbe50-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dbe50-113">Return Value</span></span>  
 <span data-ttu-id="dbe50-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="dbe50-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe50-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbe50-115">Requirements</span></span>  
 <span data-ttu-id="dbe50-116">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="dbe50-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe50-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbe50-117">See also</span></span>

- [<span data-ttu-id="dbe50-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbe50-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="dbe50-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbe50-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="dbe50-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="dbe50-120">ALink API</span></span>](index.md)
