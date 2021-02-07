---
description: 'Más información sobre: método Getpublickeytoken ('
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
ms.openlocfilehash: b864c1dc61c7498ccca6aa04ef29b57a30e1a9ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718426"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="ebc73-103">GetPublicKeyToken (Método)</span><span class="sxs-lookup"><span data-stu-id="ebc73-103">GetPublicKeyToken Method</span></span>

<span data-ttu-id="ebc73-104">Recupera el token de clave pública de un contenedor de claves o keyfile determinado.</span><span class="sxs-lookup"><span data-stu-id="ebc73-104">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc73-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebc73-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebc73-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebc73-106">Parameters</span></span>  

 `pszKeyFile`  
 <span data-ttu-id="ebc73-107">Nombre de archivo de la clave.</span><span class="sxs-lookup"><span data-stu-id="ebc73-107">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="ebc73-108">Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="ebc73-108">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="ebc73-109">Dirección en la que se va a almacenar el token de clave.</span><span class="sxs-lookup"><span data-stu-id="ebc73-109">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="ebc73-110">Especifica el tamaño, en bytes, del búfer indicado por `pvPublicKeyToken` .</span><span class="sxs-lookup"><span data-stu-id="ebc73-110">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="ebc73-111">En la devolución, contiene el número real de bytes utilizados.</span><span class="sxs-lookup"><span data-stu-id="ebc73-111">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebc73-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ebc73-112">Return Value</span></span>  

 <span data-ttu-id="ebc73-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="ebc73-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc73-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebc73-114">Requirements</span></span>  

 <span data-ttu-id="ebc73-115">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="ebc73-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc73-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebc73-116">See also</span></span>

- [<span data-ttu-id="ebc73-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebc73-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ebc73-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebc73-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ebc73-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ebc73-119">ALink API</span></span>](index.md)
