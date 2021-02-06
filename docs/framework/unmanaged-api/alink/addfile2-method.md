---
description: 'Más información sobre: método Addfile2 ('
title: AddFile2 (Método)
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: d53527ecf7e8b3a99a11ea99512fbc812125de3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638618"
---
# <a name="addfile2-method"></a><span data-ttu-id="ba7bf-103">AddFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="ba7bf-103">AddFile2 Method</span></span>

<span data-ttu-id="ba7bf-104">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ba7bf-104">Adds files to the assembly.</span></span> <span data-ttu-id="ba7bf-105">También se puede usar para crear módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="ba7bf-105">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba7bf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba7bf-106">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba7bf-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba7bf-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="ba7bf-108">IDENTIFICADOR del ensamblado al que se agrega el archivo.</span><span class="sxs-lookup"><span data-stu-id="ba7bf-108">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="ba7bf-109">Nombre del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="ba7bf-109">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ba7bf-110">`FileDef`Marcas com+ como `ffContainsNoMetaData` y `ffWriteable` .</span><span class="sxs-lookup"><span data-stu-id="ba7bf-110">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="ba7bf-111">`dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba7bf-111">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="ba7bf-112">Interfaz para la interfaz de [interfaz IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ba7bf-112">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="ba7bf-113">Recibe el identificador del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="ba7bf-113">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba7bf-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba7bf-114">Return Value</span></span>  

 <span data-ttu-id="ba7bf-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba7bf-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba7bf-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba7bf-116">Requirements</span></span>  

 <span data-ttu-id="ba7bf-117">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="ba7bf-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba7bf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba7bf-118">See also</span></span>

- [<span data-ttu-id="ba7bf-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba7bf-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ba7bf-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba7bf-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ba7bf-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ba7bf-121">ALink API</span></span>](index.md)
