---
description: 'Más información acerca de: AddFile (método)'
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
ms.openlocfilehash: 5e1253587298b2c1559c72dced43ec70dc169090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638631"
---
# <a name="addfile-method"></a><span data-ttu-id="635ec-103">Método AddFile</span><span class="sxs-lookup"><span data-stu-id="635ec-103">AddFile Method</span></span>

<span data-ttu-id="635ec-104">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="635ec-104">Adds files to the assembly.</span></span> <span data-ttu-id="635ec-105">También se puede usar para crear módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="635ec-105">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635ec-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="635ec-106">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="635ec-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="635ec-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="635ec-108">IDENTIFICADOR único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="635ec-108">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="635ec-109">Nombre completo del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="635ec-109">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="635ec-110">Marcas de FileDef COM+ como `ffContainsNoMetaData` y `ffWriteable` .</span><span class="sxs-lookup"><span data-stu-id="635ec-110">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="635ec-111">`dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="635ec-111">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="635ec-112">[IMetaDataEmit](../metadata/imetadataemit-interface.md) interfaz interface que se va a usar para emitir metadatos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="635ec-112">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="635ec-113">Puntero al lugar donde se almacenará el identificador único del archivo agregado.</span><span class="sxs-lookup"><span data-stu-id="635ec-113">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="635ec-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="635ec-114">Return Value</span></span>  

 <span data-ttu-id="635ec-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="635ec-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="635ec-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="635ec-116">Requirements</span></span>  

 <span data-ttu-id="635ec-117">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="635ec-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635ec-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="635ec-118">See also</span></span>

- [<span data-ttu-id="635ec-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="635ec-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="635ec-120">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="635ec-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="635ec-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="635ec-121">ALink API</span></span>](index.md)
