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
ms.openlocfilehash: 078820649543479e65ec35daa6e1cc2876581ddc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693208"
---
# <a name="addfile2-method"></a><span data-ttu-id="76546-102">AddFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="76546-102">AddFile2 Method</span></span>
<span data-ttu-id="76546-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="76546-103">Adds files to the assembly.</span></span> <span data-ttu-id="76546-104">También puede utilizarse para crear módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="76546-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76546-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76546-105">Syntax</span></span>  
  
```  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76546-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76546-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="76546-107">Id. del ensamblado al que se agrega el archivo.</span><span class="sxs-lookup"><span data-stu-id="76546-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="76546-108">Nombre del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="76546-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="76546-109">COM + `FileDef` marcas como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="76546-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="76546-110">`dwFlags` se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="76546-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="76546-111">Interfaz para [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="76546-111">Interface to [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="76546-112">Recibe el identificador del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="76546-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76546-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76546-113">Return Value</span></span>  
 <span data-ttu-id="76546-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="76546-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76546-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76546-115">Requirements</span></span>  
 <span data-ttu-id="76546-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="76546-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76546-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="76546-117">See also</span></span>
- [<span data-ttu-id="76546-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76546-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="76546-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76546-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="76546-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="76546-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
