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
ms.openlocfilehash: 8cb1f985c1d735fa20507ab90d478e97025c9e2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-method"></a><span data-ttu-id="a1d7a-102">LinkResource (Método)</span><span class="sxs-lookup"><span data-stu-id="a1d7a-102">LinkResource Method</span></span>
<span data-ttu-id="a1d7a-103">Vínculos de un recurso.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1d7a-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1d7a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1d7a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a1d7a-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="a1d7a-107">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="a1d7a-108">Nuevo nombre de archivo opcional.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-108">Optional new file name.</span></span> <span data-ttu-id="a1d7a-109">Si no es NULL, `pszFileName` se copiará en pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="a1d7a-110">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a1d7a-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="a1d7a-112">Este parámetro se puede pasar a [DefineManifestResource (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1d7a-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1d7a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a1d7a-113">Return Value</span></span>  
 <span data-ttu-id="a1d7a-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d7a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1d7a-115">Requirements</span></span>  
 <span data-ttu-id="a1d7a-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="a1d7a-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d7a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1d7a-117">See Also</span></span>  
 [<span data-ttu-id="a1d7a-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1d7a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a1d7a-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1d7a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a1d7a-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a1d7a-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
