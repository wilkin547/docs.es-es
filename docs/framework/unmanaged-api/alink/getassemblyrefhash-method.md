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
ms.openlocfilehash: ccf60d067af356dda1870a2fb1dcca21966f16a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401491"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="91c3c-102">GetAssemblyRefHash (Método)</span><span class="sxs-lookup"><span data-stu-id="91c3c-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="91c3c-103">Recupera un blob de hash de un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="91c3c-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91c3c-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91c3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91c3c-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="91c3c-106">Identificador del ensamblado al que hará referencia el hash.</span><span class="sxs-lookup"><span data-stu-id="91c3c-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="91c3c-107">Recibe el blob de hash resultante.</span><span class="sxs-lookup"><span data-stu-id="91c3c-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="91c3c-108">Recibe el tamaño, en bytes, del blob de hash.</span><span class="sxs-lookup"><span data-stu-id="91c3c-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91c3c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="91c3c-109">Return Value</span></span>  
 <span data-ttu-id="91c3c-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="91c3c-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91c3c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91c3c-111">Requirements</span></span>  
 <span data-ttu-id="91c3c-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="91c3c-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c3c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="91c3c-113">See Also</span></span>  
 [<span data-ttu-id="91c3c-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91c3c-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="91c3c-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91c3c-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="91c3c-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="91c3c-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
