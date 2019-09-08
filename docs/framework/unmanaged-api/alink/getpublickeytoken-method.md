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
ms.openlocfilehash: 158ecc036d56e2ad9a3fa650677c04ebcbfd7696
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777219"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="9014a-102">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="9014a-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="9014a-103">Recupera el token de clave pública de un contenedor de claves o keyfile determinado.</span><span class="sxs-lookup"><span data-stu-id="9014a-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9014a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9014a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9014a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9014a-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="9014a-106">Nombre de archivo de la clave.</span><span class="sxs-lookup"><span data-stu-id="9014a-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="9014a-107">Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="9014a-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="9014a-108">Dirección en la que se va a almacenar el token de clave.</span><span class="sxs-lookup"><span data-stu-id="9014a-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="9014a-109">Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="9014a-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="9014a-110">En la devolución, contiene el número real de bytes utilizados.</span><span class="sxs-lookup"><span data-stu-id="9014a-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9014a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9014a-111">Return Value</span></span>  
 <span data-ttu-id="9014a-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="9014a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9014a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9014a-113">Requirements</span></span>  
 <span data-ttu-id="9014a-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="9014a-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9014a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9014a-115">See also</span></span>

- [<span data-ttu-id="9014a-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9014a-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9014a-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9014a-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9014a-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="9014a-118">ALink API</span></span>](index.md)
