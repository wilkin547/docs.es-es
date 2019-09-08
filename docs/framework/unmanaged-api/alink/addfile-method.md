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
ms.openlocfilehash: b1406c68f1f6abff4d140b131f5f630d0fd767e1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787688"
---
# <a name="addfile-method"></a><span data-ttu-id="e142d-102">Método AddFile</span><span class="sxs-lookup"><span data-stu-id="e142d-102">AddFile Method</span></span>
<span data-ttu-id="e142d-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e142d-103">Adds files to the assembly.</span></span> <span data-ttu-id="e142d-104">También se puede usar para crear módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="e142d-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e142d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e142d-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e142d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e142d-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e142d-107">IDENTIFICADOR único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="e142d-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="e142d-108">Nombre completo del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="e142d-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e142d-109">Marcas `ffContainsNoMetaData` de FileDef com+ como y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="e142d-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="e142d-110">`dwFlags`se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="e142d-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="e142d-111">[IMetaDataEmit](../metadata/imetadataemit-interface.md) interfaz interface que se va a usar para emitir metadatos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e142d-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="e142d-112">Puntero al lugar donde se almacenará el identificador único del archivo agregado.</span><span class="sxs-lookup"><span data-stu-id="e142d-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e142d-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e142d-113">Return Value</span></span>  
 <span data-ttu-id="e142d-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="e142d-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e142d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e142d-115">Requirements</span></span>  
 <span data-ttu-id="e142d-116">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="e142d-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e142d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e142d-117">See also</span></span>

- [<span data-ttu-id="e142d-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e142d-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e142d-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e142d-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e142d-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e142d-120">ALink API</span></span>](index.md)
