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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789875"
---
# <a name="getfiledef-method"></a><span data-ttu-id="0b1ed-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="0b1ed-102">GetFileDef Method</span></span>
<span data-ttu-id="0b1ed-103">Recupera el token de FileDef real utilizado en los metadatos (a diferencia de lo token asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="0b1ed-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b1ed-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b1ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b1ed-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0b1ed-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0b1ed-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="0b1ed-107">Token del archivo agregado recuperados del método AddFile o AddImport (método).</span><span class="sxs-lookup"><span data-stu-id="0b1ed-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="0b1ed-108">Recibe el token FileDef.</span><span class="sxs-lookup"><span data-stu-id="0b1ed-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b1ed-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0b1ed-109">Return Value</span></span>  
 <span data-ttu-id="0b1ed-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="0b1ed-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b1ed-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b1ed-111">Requirements</span></span>  
 <span data-ttu-id="0b1ed-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="0b1ed-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1ed-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b1ed-113">See also</span></span>

- [<span data-ttu-id="0b1ed-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b1ed-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0b1ed-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b1ed-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0b1ed-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="0b1ed-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
