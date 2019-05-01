---
title: SetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dec04fa267c61798a3340e9d1e18150b812e9eaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949011"
---
# <a name="setpekind-method"></a><span data-ttu-id="609cc-102">SetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="609cc-102">SetPEKind Method</span></span>
<span data-ttu-id="609cc-103">Determina el tipo de ejecutable portable, específicas del equipo o independiente del equipo.</span><span class="sxs-lookup"><span data-stu-id="609cc-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="609cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="609cc-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="609cc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="609cc-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="609cc-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="609cc-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="609cc-107">Símbolo (token) de archivo para el que se establecerá el tipo de PE.</span><span class="sxs-lookup"><span data-stu-id="609cc-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="609cc-108">Puede ser NULL si `AssemblyID` no indica un netmodule independiente.</span><span class="sxs-lookup"><span data-stu-id="609cc-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="609cc-109">El tipo de PE, tal y como indica la [CorPEKind (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="609cc-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="609cc-110">Arquitectura del equipo de destino, como se indica en el encabezado NT.</span><span class="sxs-lookup"><span data-stu-id="609cc-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="609cc-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="609cc-111">Return Value</span></span>  
 <span data-ttu-id="609cc-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="609cc-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="609cc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="609cc-113">Requirements</span></span>  
 <span data-ttu-id="609cc-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="609cc-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609cc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="609cc-115">See also</span></span>

- [<span data-ttu-id="609cc-116">GetPEKind (método)</span><span class="sxs-lookup"><span data-stu-id="609cc-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="609cc-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="609cc-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="609cc-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="609cc-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="609cc-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="609cc-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
