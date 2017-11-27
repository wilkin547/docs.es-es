---
title: "GetPublicKeyToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetPublicKeyToken
api_location: alink.dll
api_type: COM
f1_keywords: GetPublicKeyToken
helpviewer_keywords: GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f41c8088f095802cf35239afab279d6324adb55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="43e5e-102">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="43e5e-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="43e5e-103">Recupera el token de clave pública para un determinado archivo de clave o un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="43e5e-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43e5e-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43e5e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43e5e-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="43e5e-106">Nombre de archivo de la clave.</span><span class="sxs-lookup"><span data-stu-id="43e5e-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="43e5e-107">Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="43e5e-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="43e5e-108">Dirección donde se almacenará el token de clave.</span><span class="sxs-lookup"><span data-stu-id="43e5e-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="43e5e-109">Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="43e5e-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="43e5e-110">Tras la devolución, contiene el número real de bytes que se usa.</span><span class="sxs-lookup"><span data-stu-id="43e5e-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43e5e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43e5e-111">Return Value</span></span>  
 <span data-ttu-id="43e5e-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="43e5e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e5e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43e5e-113">Requirements</span></span>  
 <span data-ttu-id="43e5e-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="43e5e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e5e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="43e5e-115">See Also</span></span>  
 [<span data-ttu-id="43e5e-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43e5e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="43e5e-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43e5e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="43e5e-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="43e5e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
