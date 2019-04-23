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
ms.openlocfilehash: 6e851c1bd56c0e9ece02fb06c0dcd9975a5b02ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079441"
---
# <a name="linkresource-method"></a><span data-ttu-id="9a0fb-102">LinkResource (Método)</span><span class="sxs-lookup"><span data-stu-id="9a0fb-102">LinkResource Method</span></span>
<span data-ttu-id="9a0fb-103">Vínculos de un recurso.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a0fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a0fb-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a0fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a0fb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9a0fb-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="9a0fb-107">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="9a0fb-108">Nuevo nombre de archivo opcional.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-108">Optional new file name.</span></span> <span data-ttu-id="9a0fb-109">Si no es NULL, `pszFileName` se copiarán en pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="9a0fb-110">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9a0fb-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="9a0fb-112">Este parámetro puede pasarse a [DefineManifestResource (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fb-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a0fb-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a0fb-113">Return Value</span></span>  
 <span data-ttu-id="9a0fb-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a0fb-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a0fb-115">Requirements</span></span>  
 <span data-ttu-id="9a0fb-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="9a0fb-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0fb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a0fb-117">See also</span></span>

- [<span data-ttu-id="9a0fb-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a0fb-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9a0fb-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a0fb-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9a0fb-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="9a0fb-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
