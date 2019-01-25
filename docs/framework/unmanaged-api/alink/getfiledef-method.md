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
ms.openlocfilehash: c6a8a9aedc5c2b09c6e6f6014142bce44f3a8297
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668605"
---
# <a name="getfiledef-method"></a><span data-ttu-id="898e8-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="898e8-102">GetFileDef Method</span></span>
<span data-ttu-id="898e8-103">Recupera el token de FileDef real utilizado en los metadatos (a diferencia de lo token asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="898e8-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="898e8-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="898e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="898e8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="898e8-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="898e8-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="898e8-107">Token del archivo agregado recuperados del método AddFile o AddImport (método).</span><span class="sxs-lookup"><span data-stu-id="898e8-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="898e8-108">Recibe el token FileDef.</span><span class="sxs-lookup"><span data-stu-id="898e8-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="898e8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="898e8-109">Return Value</span></span>  
 <span data-ttu-id="898e8-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="898e8-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898e8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="898e8-111">Requirements</span></span>  
 <span data-ttu-id="898e8-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="898e8-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898e8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="898e8-113">See also</span></span>
- [<span data-ttu-id="898e8-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="898e8-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="898e8-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="898e8-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="898e8-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="898e8-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
