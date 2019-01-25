---
title: GetAssemblyRefHash (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5698e5555e82fd8f64fd029f78cda361a367ca7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585229"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="ebb1d-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="ebb1d-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="ebb1d-103">Recupera un blob de hash para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="ebb1d-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebb1d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebb1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebb1d-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="ebb1d-106">Identificador del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="ebb1d-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="ebb1d-107">Recibe el blob de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="ebb1d-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="ebb1d-108">Recibe el tamaño, en bytes, del blob de hash.</span><span class="sxs-lookup"><span data-stu-id="ebb1d-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebb1d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ebb1d-109">Return Value</span></span>  
 <span data-ttu-id="ebb1d-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="ebb1d-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebb1d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebb1d-111">Requirements</span></span>  
 <span data-ttu-id="ebb1d-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="ebb1d-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb1d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebb1d-113">See also</span></span>
- [<span data-ttu-id="ebb1d-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebb1d-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ebb1d-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebb1d-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ebb1d-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ebb1d-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
