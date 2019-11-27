---
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
ms.openlocfilehash: 9e91d990a8f23335248043c59eb210e8c4155e3a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445632"
---
# <a name="linkresource-method"></a><span data-ttu-id="655dd-102">LinkResource (Método)</span><span class="sxs-lookup"><span data-stu-id="655dd-102">LinkResource Method</span></span>
<span data-ttu-id="655dd-103">Vínculos en un recurso.</span><span class="sxs-lookup"><span data-stu-id="655dd-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="655dd-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="655dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="655dd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="655dd-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="655dd-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="655dd-107">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="655dd-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="655dd-108">Nuevo nombre de archivo opcional.</span><span class="sxs-lookup"><span data-stu-id="655dd-108">Optional new file name.</span></span> <span data-ttu-id="655dd-109">Si no es NULL, `pszFileName` se copiará en pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="655dd-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="655dd-110">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="655dd-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="655dd-111">Marcas de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="655dd-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="655dd-112">Este parámetro se puede pasar al [método DefineManifestResource (](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="655dd-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="655dd-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="655dd-113">Return Value</span></span>  
 <span data-ttu-id="655dd-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="655dd-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="655dd-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="655dd-115">Requirements</span></span>  
 <span data-ttu-id="655dd-116">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="655dd-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655dd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="655dd-117">See also</span></span>

- [<span data-ttu-id="655dd-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="655dd-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="655dd-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="655dd-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="655dd-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="655dd-120">ALink API</span></span>](index.md)
