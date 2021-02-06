---
description: 'Más información sobre: método embedresource ('
title: EmbedResource (Método)
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: f7896172e7416048352788caf7e092096924b7af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638358"
---
# <a name="embedresource-method"></a><span data-ttu-id="f6bb3-103">EmbedResource (Método)</span><span class="sxs-lookup"><span data-stu-id="f6bb3-103">EmbedResource Method</span></span>

<span data-ttu-id="f6bb3-104">Declara un recurso incrustado.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-104">Declares an embedded resource.</span></span> <span data-ttu-id="f6bb3-105">Este método no inserta realmente el recurso.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-105">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6bb3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6bb3-106">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6bb3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6bb3-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f6bb3-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-108">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f6bb3-109">Token de archivo o ID. de ensamblado del archivo que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-109">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="f6bb3-110">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-110">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="f6bb3-111">Desplazamiento del recurso desde RVA.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-111">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f6bb3-112">Marcas de accesibilidad como `mrPublic` y `mrPrivate` .</span><span class="sxs-lookup"><span data-stu-id="f6bb3-112">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="f6bb3-113">Estas marcas se pueden pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="f6bb3-113">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6bb3-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f6bb3-114">Return Value</span></span>  

 <span data-ttu-id="f6bb3-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6bb3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6bb3-116">Requirements</span></span>  

 <span data-ttu-id="f6bb3-117">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="f6bb3-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6bb3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6bb3-118">See also</span></span>

- [<span data-ttu-id="f6bb3-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6bb3-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f6bb3-120">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6bb3-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f6bb3-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f6bb3-121">ALink API</span></span>](index.md)
