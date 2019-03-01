---
title: AddImport (Método)
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95a434cc365e12aa19d164951726ddad8945f60d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974138"
---
# <a name="addimport-method"></a><span data-ttu-id="fd708-102">AddImport (Método)</span><span class="sxs-lookup"><span data-stu-id="fd708-102">AddImport Method</span></span>
<span data-ttu-id="fd708-103">Agrega las importaciones al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd708-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd708-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd708-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd708-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd708-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fd708-106">Identificador único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="fd708-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="fd708-107">Identificador único, se recuperan de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del archivo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="fd708-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fd708-108">COM + FileDef marcas como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="fd708-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="fd708-109">`dwFlags` se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="fd708-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="fd708-110">Puntero al token que recibe el Id. del archivo resultante.</span><span class="sxs-lookup"><span data-stu-id="fd708-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd708-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd708-111">Return Value</span></span>  
 <span data-ttu-id="fd708-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="fd708-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd708-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd708-113">Requirements</span></span>  
 <span data-ttu-id="fd708-114">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="fd708-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd708-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd708-115">See also</span></span>
- [<span data-ttu-id="fd708-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd708-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fd708-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd708-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fd708-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="fd708-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
