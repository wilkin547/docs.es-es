---
title: Método AddFile
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
ms.openlocfilehash: 056d1ac0ffd3ad7fa7cb1f86ae13331ac38b3eff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162220"
---
# <a name="addfile-method"></a><span data-ttu-id="d1159-102">Método AddFile</span><span class="sxs-lookup"><span data-stu-id="d1159-102">AddFile Method</span></span>
<span data-ttu-id="d1159-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d1159-103">Adds files to the assembly.</span></span> <span data-ttu-id="d1159-104">También puede utilizarse para crear módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="d1159-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1159-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1159-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1159-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1159-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d1159-107">Identificador único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="d1159-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="d1159-108">Nombre completo del archivo que se agregará.</span><span class="sxs-lookup"><span data-stu-id="d1159-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d1159-109">COM + FileDef marcas como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="d1159-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> `dwFlags` <span data-ttu-id="d1159-110">se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="d1159-110">is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="d1159-111">[IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz que se usará para emitir metadatos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="d1159-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="d1159-112">Puntero a donde se almacenará el identificador único del archivo agregado.</span><span class="sxs-lookup"><span data-stu-id="d1159-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1159-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d1159-113">Return Value</span></span>  
 <span data-ttu-id="d1159-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="d1159-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1159-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1159-115">Requirements</span></span>  
 <span data-ttu-id="d1159-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="d1159-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1159-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1159-117">See also</span></span>

- [<span data-ttu-id="d1159-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1159-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d1159-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1159-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d1159-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d1159-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
