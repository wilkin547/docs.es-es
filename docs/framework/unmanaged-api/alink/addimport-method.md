---
title: AddImport Method1
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
ms.openlocfilehash: 98fefc0240f6496a3e7bfb491e27a57e98cfea1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404071"
---
# <a name="addimport-method1"></a><span data-ttu-id="7309a-102">AddImport Method1</span><span class="sxs-lookup"><span data-stu-id="7309a-102">AddImport Method1</span></span>
<span data-ttu-id="7309a-103">Agrega las importaciones al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7309a-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7309a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7309a-104">Syntax</span></span>  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7309a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7309a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7309a-106">Identificador único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="7309a-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="7309a-107">Identificador único, se recupera de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), del archivo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="7309a-107">Unique ID, retrieved from [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7309a-108">COM + FileDef se marca como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="7309a-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="7309a-109">`dwFlags` se pasa a [DefineFile (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="7309a-109">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="7309a-110">Puntero al token que recibe el identificador para el archivo resultante.</span><span class="sxs-lookup"><span data-stu-id="7309a-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7309a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7309a-111">Return Value</span></span>  
 <span data-ttu-id="7309a-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="7309a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7309a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7309a-113">Requirements</span></span>  
 <span data-ttu-id="7309a-114">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="7309a-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7309a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7309a-115">See Also</span></span>  
 [<span data-ttu-id="7309a-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7309a-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="7309a-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7309a-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="7309a-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="7309a-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
