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
ms.openlocfilehash: a51e8c83d0949f68a41f6a4e10396adbc4f3c9c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741893"
---
# <a name="getfiledef-method"></a><span data-ttu-id="ac0a0-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="ac0a0-102">GetFileDef Method</span></span>
<span data-ttu-id="ac0a0-103">Recupera el token de FileDef real utilizado en los metadatos (a diferencia de lo token asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="ac0a0-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac0a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac0a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac0a0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ac0a0-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac0a0-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="ac0a0-107">Token del archivo agregado recuperados del método AddFile o AddImport (método).</span><span class="sxs-lookup"><span data-stu-id="ac0a0-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="ac0a0-108">Recibe el token FileDef.</span><span class="sxs-lookup"><span data-stu-id="ac0a0-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac0a0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac0a0-109">Return Value</span></span>  
 <span data-ttu-id="ac0a0-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="ac0a0-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0a0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac0a0-111">Requirements</span></span>  
 <span data-ttu-id="ac0a0-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="ac0a0-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0a0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac0a0-113">See also</span></span>

- [<span data-ttu-id="ac0a0-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac0a0-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ac0a0-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac0a0-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ac0a0-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ac0a0-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
