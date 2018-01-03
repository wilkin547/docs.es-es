---
title: "LinkResource (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.LinkResource
api_location: alink.dll
api_type: COM
f1_keywords: LinkResource
helpviewer_keywords: LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1ff38bf0017cf400d8f35f0ddf265f8628c82d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="linkresource-method"></a><span data-ttu-id="66606-102">LinkResource (Método)</span><span class="sxs-lookup"><span data-stu-id="66606-102">LinkResource Method</span></span>
<span data-ttu-id="66606-103">Vínculos de un recurso.</span><span class="sxs-lookup"><span data-stu-id="66606-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66606-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66606-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66606-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66606-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="66606-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="66606-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="66606-107">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="66606-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="66606-108">Nuevo nombre de archivo opcional.</span><span class="sxs-lookup"><span data-stu-id="66606-108">Optional new file name.</span></span> <span data-ttu-id="66606-109">Si no es NULL, `pszFileName` se copiará en pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="66606-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="66606-110">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="66606-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="66606-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="66606-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="66606-112">Este parámetro se puede pasar a [DefineManifestResource (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="66606-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66606-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="66606-113">Return Value</span></span>  
 <span data-ttu-id="66606-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="66606-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66606-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66606-115">Requirements</span></span>  
 <span data-ttu-id="66606-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="66606-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66606-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="66606-117">See Also</span></span>  
 [<span data-ttu-id="66606-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66606-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="66606-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66606-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="66606-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="66606-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
