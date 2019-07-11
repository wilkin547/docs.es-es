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
ms.openlocfilehash: 49ea7fbe9f491028a85fae543d126fd9d4f2d940
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741910"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="41ec3-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="41ec3-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="41ec3-103">Recupera un blob de hash para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="41ec3-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41ec3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41ec3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="41ec3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41ec3-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="41ec3-106">Identificador del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="41ec3-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="41ec3-107">Recibe el blob de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="41ec3-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="41ec3-108">Recibe el tamaño, en bytes, del blob de hash.</span><span class="sxs-lookup"><span data-stu-id="41ec3-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41ec3-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41ec3-109">Return Value</span></span>  
 <span data-ttu-id="41ec3-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="41ec3-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41ec3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41ec3-111">Requirements</span></span>  
 <span data-ttu-id="41ec3-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="41ec3-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ec3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="41ec3-113">See also</span></span>

- [<span data-ttu-id="41ec3-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41ec3-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="41ec3-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41ec3-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="41ec3-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="41ec3-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
