---
title: "GetFileDef (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetFileDef
api_location: alink.dll
api_type: COM
f1_keywords: GetFileDef
helpviewer_keywords: GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 473cbaba8712ee247733ba3075c0163e259cf4dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getfiledef-method"></a><span data-ttu-id="00015-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="00015-102">GetFileDef Method</span></span>
<span data-ttu-id="00015-103">Recupera el token FileDef real que se utiliza en los metadatos (en lugar del símbolo (token) asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="00015-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00015-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00015-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00015-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00015-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="00015-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="00015-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="00015-107">Símbolo (token) del archivo agregado recuperados AddFile (método) o addImport (método).</span><span class="sxs-lookup"><span data-stu-id="00015-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="00015-108">Recibe el símbolo (token) de FileDef.</span><span class="sxs-lookup"><span data-stu-id="00015-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00015-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="00015-109">Return Value</span></span>  
 <span data-ttu-id="00015-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="00015-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00015-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00015-111">Requirements</span></span>  
 <span data-ttu-id="00015-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="00015-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00015-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="00015-113">See Also</span></span>  
 [<span data-ttu-id="00015-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00015-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="00015-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00015-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="00015-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="00015-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
