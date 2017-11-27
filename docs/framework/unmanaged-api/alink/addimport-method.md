---
title: AddImport Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AddImport
- IALink.AddImport
api_location: alink.dll
api_type: COM
f1_keywords: AddImport
helpviewer_keywords: AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd0e55cab6f0fdb7f971d7cf06e5703340e32307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="addimport-method1"></a><span data-ttu-id="1c5d6-102">AddImport Method1</span><span class="sxs-lookup"><span data-stu-id="1c5d6-102">AddImport Method1</span></span>
<span data-ttu-id="1c5d6-103">Agrega las importaciones al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c5d6-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c5d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c5d6-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c5d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c5d6-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1c5d6-106">Identificador único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="1c5d6-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="1c5d6-107">Identificador único, se recupera de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del archivo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="1c5d6-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1c5d6-108">COM + FileDef se marca como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="1c5d6-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="1c5d6-109">`dwFlags`se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="1c5d6-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="1c5d6-110">Puntero al token que recibe el identificador para el archivo resultante.</span><span class="sxs-lookup"><span data-stu-id="1c5d6-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c5d6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1c5d6-111">Return Value</span></span>  
 <span data-ttu-id="1c5d6-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="1c5d6-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c5d6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c5d6-113">Requirements</span></span>  
 <span data-ttu-id="1c5d6-114">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="1c5d6-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5d6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c5d6-115">See Also</span></span>  
 [<span data-ttu-id="1c5d6-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c5d6-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1c5d6-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c5d6-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1c5d6-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1c5d6-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
