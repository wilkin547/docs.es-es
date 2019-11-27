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
ms.openlocfilehash: 2e7ed4e1529104db30b0b06665f74342d9ca9a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447243"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="642b6-102">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="642b6-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="642b6-103">Recupera el token de clave pública de un contenedor de claves o keyfile determinado.</span><span class="sxs-lookup"><span data-stu-id="642b6-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="642b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="642b6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="642b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="642b6-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="642b6-106">Nombre de archivo de la clave.</span><span class="sxs-lookup"><span data-stu-id="642b6-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="642b6-107">Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="642b6-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="642b6-108">Dirección en la que se va a almacenar el token de clave.</span><span class="sxs-lookup"><span data-stu-id="642b6-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="642b6-109">Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="642b6-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="642b6-110">En la devolución, contiene el número real de bytes utilizados.</span><span class="sxs-lookup"><span data-stu-id="642b6-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="642b6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="642b6-111">Return Value</span></span>  
 <span data-ttu-id="642b6-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="642b6-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="642b6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="642b6-113">Requirements</span></span>  
 <span data-ttu-id="642b6-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="642b6-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642b6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="642b6-115">See also</span></span>

- [<span data-ttu-id="642b6-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="642b6-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="642b6-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="642b6-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="642b6-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="642b6-118">ALink API</span></span>](index.md)
