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
ms.openlocfilehash: 335d80255f7a3f5a22e8a69aa91c9e5b0843ea1e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741589"
---
# <a name="linkresource-method"></a><span data-ttu-id="6f252-102">LinkResource (Método)</span><span class="sxs-lookup"><span data-stu-id="6f252-102">LinkResource Method</span></span>
<span data-ttu-id="6f252-103">Vínculos de un recurso.</span><span class="sxs-lookup"><span data-stu-id="6f252-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f252-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f252-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f252-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f252-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6f252-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6f252-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="6f252-107">Nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="6f252-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="6f252-108">Nuevo nombre de archivo opcional.</span><span class="sxs-lookup"><span data-stu-id="6f252-108">Optional new file name.</span></span> <span data-ttu-id="6f252-109">Si no es NULL, `pszFileName` se copiarán en pszNewLocation.</span><span class="sxs-lookup"><span data-stu-id="6f252-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="6f252-110">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="6f252-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6f252-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="6f252-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="6f252-112">Este parámetro puede pasarse a [DefineManifestResource (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span><span class="sxs-lookup"><span data-stu-id="6f252-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f252-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6f252-113">Return Value</span></span>  
 <span data-ttu-id="6f252-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="6f252-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f252-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f252-115">Requirements</span></span>  
 <span data-ttu-id="6f252-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="6f252-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f252-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f252-117">See also</span></span>

- [<span data-ttu-id="6f252-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f252-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6f252-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f252-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6f252-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="6f252-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
