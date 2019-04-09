---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef7d6272c04c3edab8ef652bcb2759861ff2b982
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129576"
---
# <a name="embedresource-method"></a><span data-ttu-id="21d3b-102">EmbedResource (Método)</span><span class="sxs-lookup"><span data-stu-id="21d3b-102">EmbedResource Method</span></span>
<span data-ttu-id="21d3b-103">Declara un recurso incrustado.</span><span class="sxs-lookup"><span data-stu-id="21d3b-103">Declares an embedded resource.</span></span> <span data-ttu-id="21d3b-104">Este método realmente no incrustar el recurso.</span><span class="sxs-lookup"><span data-stu-id="21d3b-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d3b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21d3b-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="21d3b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21d3b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="21d3b-107">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="21d3b-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="21d3b-108">Archivo de token o identificador de ensamblado del archivo que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="21d3b-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="21d3b-109">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="21d3b-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="21d3b-110">Desplazamiento del recurso desde la RVA.</span><span class="sxs-lookup"><span data-stu-id="21d3b-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="21d3b-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="21d3b-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="21d3b-112">Estas marcas se pueden pasar a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="21d3b-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21d3b-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21d3b-113">Return Value</span></span>  
 <span data-ttu-id="21d3b-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="21d3b-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21d3b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21d3b-115">Requirements</span></span>  
 <span data-ttu-id="21d3b-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="21d3b-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d3b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="21d3b-117">See also</span></span>

- [<span data-ttu-id="21d3b-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21d3b-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="21d3b-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21d3b-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="21d3b-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="21d3b-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
