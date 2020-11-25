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
ms.openlocfilehash: cf73ada36be66edb3fa267d61873ae9acb088a34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717050"
---
# <a name="addimport-method"></a><span data-ttu-id="0d423-102">Método AddImport</span><span class="sxs-lookup"><span data-stu-id="0d423-102">AddImport Method</span></span>

<span data-ttu-id="0d423-103">Agrega importaciones al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d423-103">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d423-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d423-104">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d423-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d423-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="0d423-106">IDENTIFICADOR único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="0d423-106">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="0d423-107">IDENTIFICADOR único, recuperado del [método importFile](importfile-method.md), del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="0d423-107">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0d423-108">Marcas de FileDef COM+ como `ffContainsNoMetaData` y `ffWriteable` .</span><span class="sxs-lookup"><span data-stu-id="0d423-108">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="0d423-109">`dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="0d423-109">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="0d423-110">Puntero al token que recibe el identificador del archivo resultante.</span><span class="sxs-lookup"><span data-stu-id="0d423-110">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d423-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0d423-111">Return Value</span></span>  

 <span data-ttu-id="0d423-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d423-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d423-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d423-113">Requirements</span></span>  

 <span data-ttu-id="0d423-114">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="0d423-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d423-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d423-115">See also</span></span>

- [<span data-ttu-id="0d423-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d423-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0d423-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d423-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0d423-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="0d423-118">ALink API</span></span>](index.md)
