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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b0b5c6e70afffd12d3f0cdbbb92b20ac3a949e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635018"
---
# <a name="linkresource-method"></a><span data-ttu-id="ae6b2-102">LinkResource (Método)</span><span class="sxs-lookup"><span data-stu-id="ae6b2-102">LinkResource Method</span></span>
<span data-ttu-id="ae6b2-103">Vínculos de un recurso.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae6b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae6b2-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae6b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae6b2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ae6b2-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="ae6b2-107">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="ae6b2-108">Nuevo nombre de archivo opcional.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-108">Optional new file name.</span></span> <span data-ttu-id="ae6b2-109">Si no es NULL, `pszFileName` se copiarán en pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="ae6b2-110">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ae6b2-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="ae6b2-112">Este parámetro puede pasarse a [DefineManifestResource (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="ae6b2-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae6b2-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae6b2-113">Return Value</span></span>  
 <span data-ttu-id="ae6b2-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae6b2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae6b2-115">Requirements</span></span>  
 <span data-ttu-id="ae6b2-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="ae6b2-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae6b2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae6b2-117">See also</span></span>
- [<span data-ttu-id="ae6b2-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae6b2-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ae6b2-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae6b2-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ae6b2-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ae6b2-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
