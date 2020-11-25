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
ms.openlocfilehash: e41be6407076a2609a83a5be3b0c42d28914ec38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720347"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="cef2e-102">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="cef2e-102">GetPublicKeyToken Method</span></span>

<span data-ttu-id="cef2e-103">Recupera el token de clave pública de un contenedor de claves o keyfile determinado.</span><span class="sxs-lookup"><span data-stu-id="cef2e-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cef2e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cef2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cef2e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cef2e-105">Parameters</span></span>  

 `pszKeyFile`  
 <span data-ttu-id="cef2e-106">Nombre de archivo de la clave.</span><span class="sxs-lookup"><span data-stu-id="cef2e-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="cef2e-107">Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="cef2e-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="cef2e-108">Dirección en la que se va a almacenar el token de clave.</span><span class="sxs-lookup"><span data-stu-id="cef2e-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="cef2e-109">Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken` .</span><span class="sxs-lookup"><span data-stu-id="cef2e-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="cef2e-110">En la devolución, contiene el número real de bytes utilizados.</span><span class="sxs-lookup"><span data-stu-id="cef2e-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cef2e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cef2e-111">Return Value</span></span>  

 <span data-ttu-id="cef2e-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="cef2e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cef2e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cef2e-113">Requirements</span></span>  

 <span data-ttu-id="cef2e-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="cef2e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef2e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cef2e-115">See also</span></span>

- [<span data-ttu-id="cef2e-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cef2e-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cef2e-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cef2e-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cef2e-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="cef2e-118">ALink API</span></span>](index.md)
