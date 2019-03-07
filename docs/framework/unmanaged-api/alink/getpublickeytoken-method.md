---
title: GetPublicKeyToken (Método)
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0481cfc3fa88aeb6fd7cd6ba93554d426f8eb2e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492054"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="adfc3-102">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="adfc3-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="adfc3-103">Recupera el token de clave pública para un determinado archivo de clave o un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="adfc3-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adfc3-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="adfc3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="adfc3-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="adfc3-106">Nombre de archivo de la clave.</span><span class="sxs-lookup"><span data-stu-id="adfc3-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="adfc3-107">Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="adfc3-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="adfc3-108">Dirección donde el token de clave es que se almacenará.</span><span class="sxs-lookup"><span data-stu-id="adfc3-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="adfc3-109">Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="adfc3-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="adfc3-110">Cuando se devuelve, contiene el número real de bytes utilizados.</span><span class="sxs-lookup"><span data-stu-id="adfc3-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adfc3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="adfc3-111">Return Value</span></span>  
 <span data-ttu-id="adfc3-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="adfc3-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adfc3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="adfc3-113">Requirements</span></span>  
 <span data-ttu-id="adfc3-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="adfc3-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adfc3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="adfc3-115">See also</span></span>
- [<span data-ttu-id="adfc3-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="adfc3-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="adfc3-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="adfc3-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="adfc3-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="adfc3-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
