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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790057"
---
# <a name="embedresource-method"></a><span data-ttu-id="3503c-102">EmbedResource (Método)</span><span class="sxs-lookup"><span data-stu-id="3503c-102">EmbedResource Method</span></span>
<span data-ttu-id="3503c-103">Declara un recurso incrustado.</span><span class="sxs-lookup"><span data-stu-id="3503c-103">Declares an embedded resource.</span></span> <span data-ttu-id="3503c-104">Este método realmente no incrustar el recurso.</span><span class="sxs-lookup"><span data-stu-id="3503c-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3503c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3503c-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3503c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3503c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3503c-107">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3503c-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3503c-108">Archivo de token o identificador de ensamblado del archivo que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="3503c-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="3503c-109">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="3503c-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="3503c-110">Desplazamiento del recurso desde la RVA.</span><span class="sxs-lookup"><span data-stu-id="3503c-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3503c-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="3503c-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="3503c-112">Estas marcas se pueden pasar a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="3503c-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3503c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3503c-113">Return Value</span></span>  
 <span data-ttu-id="3503c-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="3503c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3503c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3503c-115">Requirements</span></span>  
 <span data-ttu-id="3503c-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="3503c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3503c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3503c-117">See also</span></span>

- [<span data-ttu-id="3503c-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3503c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3503c-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3503c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3503c-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="3503c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
