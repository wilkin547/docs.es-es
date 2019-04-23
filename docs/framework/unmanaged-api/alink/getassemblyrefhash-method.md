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
ms.openlocfilehash: 6fa8d42f9e849db6a02f6c62b37e04cf5dee016e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119657"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="b5a6a-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="b5a6a-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="b5a6a-103">Recupera un blob de hash para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="b5a6a-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5a6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5a6a-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5a6a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5a6a-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="b5a6a-106">Identificador del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="b5a6a-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="b5a6a-107">Recibe el blob de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="b5a6a-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="b5a6a-108">Recibe el tamaño, en bytes, del blob de hash.</span><span class="sxs-lookup"><span data-stu-id="b5a6a-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5a6a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b5a6a-109">Return Value</span></span>  
 <span data-ttu-id="b5a6a-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="b5a6a-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5a6a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5a6a-111">Requirements</span></span>  
 <span data-ttu-id="b5a6a-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="b5a6a-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a6a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5a6a-113">See also</span></span>

- [<span data-ttu-id="b5a6a-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5a6a-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b5a6a-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5a6a-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b5a6a-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b5a6a-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
