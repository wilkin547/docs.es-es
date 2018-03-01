---
title: AddFile Method1
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 943ff2901ee0888860941e86d589060de729907d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="addfile-method1"></a><span data-ttu-id="0611d-102">AddFile Method1</span><span class="sxs-lookup"><span data-stu-id="0611d-102">AddFile Method1</span></span>
<span data-ttu-id="0611d-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0611d-103">Adds files to the assembly.</span></span> <span data-ttu-id="0611d-104">También puede utilizarse para crear módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="0611d-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0611d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0611d-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0611d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0611d-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0611d-107">Identificador único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="0611d-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="0611d-108">Nombre completo del archivo que se agregará.</span><span class="sxs-lookup"><span data-stu-id="0611d-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0611d-109">COM + FileDef se marca como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="0611d-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="0611d-110">`dwFlags`se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="0611d-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="0611d-111">[IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz que se usará para emitir los metadatos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0611d-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="0611d-112">Puntero a donde se almacenará el identificador único del archivo agregado.</span><span class="sxs-lookup"><span data-stu-id="0611d-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0611d-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0611d-113">Return Value</span></span>  
 <span data-ttu-id="0611d-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="0611d-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0611d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0611d-115">Requirements</span></span>  
 <span data-ttu-id="0611d-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="0611d-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0611d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0611d-117">See Also</span></span>  
 [<span data-ttu-id="0611d-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0611d-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0611d-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0611d-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0611d-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="0611d-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
