---
title: "GetAssemblyRefHash (Método)"
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
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99ae38025f223d669a428738783676ebc0687554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="123c8-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="123c8-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="123c8-103">Recupera un blob de hash de un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="123c8-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="123c8-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="123c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="123c8-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="123c8-106">Identificador del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="123c8-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="123c8-107">Recibe el blob de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="123c8-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="123c8-108">Recibe el tamaño, en bytes, del blob de hash.</span><span class="sxs-lookup"><span data-stu-id="123c8-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="123c8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="123c8-109">Return Value</span></span>  
 <span data-ttu-id="123c8-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="123c8-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="123c8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="123c8-111">Requirements</span></span>  
 <span data-ttu-id="123c8-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="123c8-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123c8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="123c8-113">See Also</span></span>  
 [<span data-ttu-id="123c8-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="123c8-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="123c8-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="123c8-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="123c8-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="123c8-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
