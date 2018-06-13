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
ms.openlocfilehash: b772ae37baed44b90e4f5420e0f7724201a56abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401816"
---
# <a name="getfiledef-method"></a><span data-ttu-id="b1f2d-102">GetFileDef (Método)</span><span class="sxs-lookup"><span data-stu-id="b1f2d-102">GetFileDef Method</span></span>
<span data-ttu-id="b1f2d-103">Recupera el token FileDef real que se utiliza en los metadatos (en lugar del símbolo (token) asignado por ALink).</span><span class="sxs-lookup"><span data-stu-id="b1f2d-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1f2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1f2d-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1f2d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1f2d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b1f2d-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b1f2d-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="b1f2d-107">Símbolo (token) del archivo agregado recuperados AddFile (método) o addImport (método).</span><span class="sxs-lookup"><span data-stu-id="b1f2d-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="b1f2d-108">Recibe el símbolo (token) de FileDef.</span><span class="sxs-lookup"><span data-stu-id="b1f2d-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1f2d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b1f2d-109">Return Value</span></span>  
 <span data-ttu-id="b1f2d-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="b1f2d-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1f2d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1f2d-111">Requirements</span></span>  
 <span data-ttu-id="b1f2d-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="b1f2d-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1f2d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1f2d-113">See Also</span></span>  
 [<span data-ttu-id="b1f2d-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1f2d-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b1f2d-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1f2d-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b1f2d-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b1f2d-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
