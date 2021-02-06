---
description: 'Más información sobre: método addImport ('
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
ms.openlocfilehash: 9dca26501e66313b0932caf1288db7c909154e1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638605"
---
# <a name="addimport-method"></a><span data-ttu-id="b881e-103">Método AddImport</span><span class="sxs-lookup"><span data-stu-id="b881e-103">AddImport Method</span></span>

<span data-ttu-id="b881e-104">Agrega importaciones al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b881e-104">Adds imports to the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b881e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b881e-105">Syntax</span></span>  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b881e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b881e-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="b881e-107">IDENTIFICADOR único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="b881e-107">Unique ID of assembly to be augmented.</span></span>  
  
 `ImportToken`  
 <span data-ttu-id="b881e-108">IDENTIFICADOR único, recuperado del [método importFile](importfile-method.md), del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="b881e-108">Unique ID, retrieved from [ImportFile Method](importfile-method.md), of file to be imported.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b881e-109">Marcas de FileDef COM+ como `ffContainsNoMetaData` y `ffWriteable` .</span><span class="sxs-lookup"><span data-stu-id="b881e-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="b881e-110">`dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="b881e-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="b881e-111">Puntero al token que recibe el identificador del archivo resultante.</span><span class="sxs-lookup"><span data-stu-id="b881e-111">Pointer to token that receives the ID for the resulting file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b881e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b881e-112">Return Value</span></span>  

 <span data-ttu-id="b881e-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="b881e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b881e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b881e-114">Requirements</span></span>  

 <span data-ttu-id="b881e-115">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="b881e-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b881e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b881e-116">See also</span></span>

- [<span data-ttu-id="b881e-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b881e-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b881e-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b881e-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b881e-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b881e-119">ALink API</span></span>](index.md)
