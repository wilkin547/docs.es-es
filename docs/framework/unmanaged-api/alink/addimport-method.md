---
title: Método AddImport
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
ms.openlocfilehash: bbe8a43f44d59249abc713c95fce31f1fb9a5993
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148673"
---
# <a name="addimport-method"></a><span data-ttu-id="8979c-102">Método AddImport</span><span class="sxs-lookup"><span data-stu-id="8979c-102">AddImport Method</span></span>
<span data-ttu-id="8979c-103">Agrega las importaciones al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8979c-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8979c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8979c-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8979c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8979c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8979c-106">Identificador único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="8979c-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="8979c-107">Identificador único, se recuperan de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del archivo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="8979c-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8979c-108">COM + FileDef marcas como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="8979c-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> `dwFlags` <span data-ttu-id="8979c-109">se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="8979c-109">is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="8979c-110">Puntero al token que recibe el Id. del archivo resultante.</span><span class="sxs-lookup"><span data-stu-id="8979c-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8979c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8979c-111">Return Value</span></span>  
 <span data-ttu-id="8979c-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="8979c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8979c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8979c-113">Requirements</span></span>  
 <span data-ttu-id="8979c-114">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="8979c-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8979c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8979c-115">See also</span></span>

- [<span data-ttu-id="8979c-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8979c-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="8979c-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8979c-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="8979c-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="8979c-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
