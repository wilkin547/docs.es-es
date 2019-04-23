---
title: GetFileDef (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9153c9b3735e265d59ba072f747c92434c95d9ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184501"
---
# <a name="getfiledef-method"></a><span data-ttu-id="054a4-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="054a4-102">GetFileDef Method</span></span>
<span data-ttu-id="054a4-103">Recupera el token de FileDef real utilizado en los metadatos (a diferencia de lo token asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="054a4-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="054a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="054a4-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="054a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="054a4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="054a4-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="054a4-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="054a4-107">Token del archivo agregado recuperados del método AddFile o AddImport (método).</span><span class="sxs-lookup"><span data-stu-id="054a4-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="054a4-108">Recibe el token FileDef.</span><span class="sxs-lookup"><span data-stu-id="054a4-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="054a4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="054a4-109">Return Value</span></span>  
 <span data-ttu-id="054a4-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="054a4-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="054a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="054a4-111">Requirements</span></span>  
 <span data-ttu-id="054a4-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="054a4-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="054a4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="054a4-113">See also</span></span>

- [<span data-ttu-id="054a4-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054a4-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="054a4-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054a4-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="054a4-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="054a4-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
