---
title: "EmbedResource (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 815e4b6abbb56b0998a12c096f0ba7cb678778ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="embedresource-method"></a><span data-ttu-id="3f920-102">EmbedResource (Método)</span><span class="sxs-lookup"><span data-stu-id="3f920-102">EmbedResource Method</span></span>
<span data-ttu-id="3f920-103">Declara un recurso incrustado.</span><span class="sxs-lookup"><span data-stu-id="3f920-103">Declares an embedded resource.</span></span> <span data-ttu-id="3f920-104">Este método no incrusta realmente el recurso.</span><span class="sxs-lookup"><span data-stu-id="3f920-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f920-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f920-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f920-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f920-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3f920-107">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3f920-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3f920-108">Símbolo (token) o ensamblado identificador del archivo que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="3f920-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="3f920-109">Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="3f920-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="3f920-110">Desplazamiento del recurso de RVA.</span><span class="sxs-lookup"><span data-stu-id="3f920-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3f920-111">Indicadores de accesibilidad como `mrPublic` y `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="3f920-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="3f920-112">Estas marcas se pueden pasar a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="3f920-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f920-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f920-113">Return Value</span></span>  
 <span data-ttu-id="3f920-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="3f920-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f920-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f920-115">Requirements</span></span>  
 <span data-ttu-id="3f920-116">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="3f920-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f920-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f920-117">See Also</span></span>  
 [<span data-ttu-id="3f920-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f920-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="3f920-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f920-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="3f920-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="3f920-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
