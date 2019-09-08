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
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787656"
---
# <a name="addimport-method"></a><span data-ttu-id="426ca-102">Método AddImport</span><span class="sxs-lookup"><span data-stu-id="426ca-102">AddImport Method</span></span>
<span data-ttu-id="426ca-103">Agrega importaciones al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="426ca-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="426ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="426ca-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="426ca-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="426ca-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="426ca-106">IDENTIFICADOR único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="426ca-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="426ca-107">IDENTIFICADOR único, recuperado del [método importFile](importfile-method.md), del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="426ca-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="426ca-108">Marcas `ffContainsNoMetaData` de FileDef com+ como y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="426ca-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="426ca-109">`dwFlags`se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="426ca-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="426ca-110">Puntero al token que recibe el identificador del archivo resultante.</span><span class="sxs-lookup"><span data-stu-id="426ca-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="426ca-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="426ca-111">Return Value</span></span>  
 <span data-ttu-id="426ca-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="426ca-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="426ca-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="426ca-113">Requirements</span></span>  
 <span data-ttu-id="426ca-114">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="426ca-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="426ca-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="426ca-115">See also</span></span>

- [<span data-ttu-id="426ca-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="426ca-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="426ca-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="426ca-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="426ca-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="426ca-118">ALink API</span></span>](index.md)
