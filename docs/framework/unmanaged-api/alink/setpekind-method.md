---
title: "SetPEKind (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetPEKind
api_location: alink.dll
api_type: COM
f1_keywords: SetPEKind
helpviewer_keywords: SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d511bcda2ab4e879c123d866b3f6c887173c1d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="setpekind-method"></a><span data-ttu-id="de3e6-102">SetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="de3e6-102">SetPEKind Method</span></span>
<span data-ttu-id="de3e6-103">Determina el tipo de archivo ejecutable portable, específicas del equipo o independiente del equipo.</span><span class="sxs-lookup"><span data-stu-id="de3e6-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de3e6-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="de3e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de3e6-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="de3e6-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="de3e6-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="de3e6-107">Símbolo (token) de archivo para el que se puede establecer el tipo de PE.</span><span class="sxs-lookup"><span data-stu-id="de3e6-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="de3e6-108">Puede ser NULL si `AssemblyID` no indica un archivo netmodule no enlazado.</span><span class="sxs-lookup"><span data-stu-id="de3e6-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="de3e6-109">El tipo de PE, tal y como indica la [CorPEKind (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="de3e6-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="de3e6-110">Arquitectura del equipo de destino, como se indica en el encabezado NT.</span><span class="sxs-lookup"><span data-stu-id="de3e6-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de3e6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="de3e6-111">Return Value</span></span>  
 <span data-ttu-id="de3e6-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="de3e6-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de3e6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de3e6-113">Requirements</span></span>  
 <span data-ttu-id="de3e6-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="de3e6-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3e6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="de3e6-115">See Also</span></span>  
 [<span data-ttu-id="de3e6-116">GetPEKind (método)</span><span class="sxs-lookup"><span data-stu-id="de3e6-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [<span data-ttu-id="de3e6-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de3e6-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="de3e6-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de3e6-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="de3e6-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="de3e6-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
