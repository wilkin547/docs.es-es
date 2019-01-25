---
title: AddFile (método1)
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84b68638ed0f7a86156cf7e5fcc98d3c02cba18a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662613"
---
# <a name="addfile-method1"></a><span data-ttu-id="6b70c-102">AddFile (método1)</span><span class="sxs-lookup"><span data-stu-id="6b70c-102">AddFile Method1</span></span>
<span data-ttu-id="6b70c-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6b70c-103">Adds files to the assembly.</span></span> <span data-ttu-id="6b70c-104">También puede utilizarse para crear módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="6b70c-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b70c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b70c-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b70c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b70c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6b70c-107">Identificador único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="6b70c-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="6b70c-108">Nombre completo del archivo que se agregará.</span><span class="sxs-lookup"><span data-stu-id="6b70c-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6b70c-109">COM + FileDef marcas como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="6b70c-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="6b70c-110">`dwFlags` se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="6b70c-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="6b70c-111">[IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz que se usará para emitir metadatos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="6b70c-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="6b70c-112">Puntero a donde se almacenará el identificador único del archivo agregado.</span><span class="sxs-lookup"><span data-stu-id="6b70c-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b70c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6b70c-113">Return Value</span></span>  
 <span data-ttu-id="6b70c-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="6b70c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b70c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b70c-115">Requirements</span></span>  
 <span data-ttu-id="6b70c-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="6b70c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b70c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b70c-117">See also</span></span>
- [<span data-ttu-id="6b70c-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b70c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6b70c-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b70c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6b70c-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="6b70c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
