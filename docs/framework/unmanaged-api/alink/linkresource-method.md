---
description: 'Más información sobre: método linkresource ('
title: LinkResource (Método)
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: ff12138433577eccbb313b8e64a329be1358ba70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662551"
---
# <a name="linkresource-method"></a><span data-ttu-id="f263a-103">LinkResource (Método)</span><span class="sxs-lookup"><span data-stu-id="f263a-103">LinkResource Method</span></span>

<span data-ttu-id="f263a-104">Vínculos en un recurso.</span><span class="sxs-lookup"><span data-stu-id="f263a-104">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f263a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f263a-105">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f263a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f263a-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f263a-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f263a-107">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="f263a-108">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="f263a-108">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="f263a-109">Nuevo nombre de archivo opcional.</span><span class="sxs-lookup"><span data-stu-id="f263a-109">Optional new file name.</span></span> <span data-ttu-id="f263a-110">Si no es NULL, se `pszFileName` copiará en pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="f263a-110">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="f263a-111">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="f263a-111">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f263a-112">Marcas de accesibilidad como `mrPublic` y `mrPrivate` .</span><span class="sxs-lookup"><span data-stu-id="f263a-112">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="f263a-113">Este parámetro se puede pasar al [método DefineManifestResource (](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="f263a-113">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f263a-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f263a-114">Return Value</span></span>  

 <span data-ttu-id="f263a-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f263a-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f263a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f263a-116">Requirements</span></span>  

 <span data-ttu-id="f263a-117">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="f263a-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f263a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f263a-118">See also</span></span>

- [<span data-ttu-id="f263a-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f263a-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f263a-120">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f263a-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f263a-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f263a-121">ALink API</span></span>](index.md)
