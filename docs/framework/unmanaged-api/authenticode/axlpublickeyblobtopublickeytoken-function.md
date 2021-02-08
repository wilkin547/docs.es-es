---
description: 'Más información acerca de: _AxlPublicKeyBlobToPublicKeyToken función'
title: _AxlPublicKeyBlobToPublicKeyToken (Función)
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
topic_type:
- apiref
ms.openlocfilehash: df0b484bad64051eb892d4898a6c90777cc2d5cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781940"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="5123c-103">\_AxlPublicKeyBlobToPublicKeyToken función)</span><span class="sxs-lookup"><span data-stu-id="5123c-103">\_AxlPublicKeyBlobToPublicKeyToken Function</span></span>

<span data-ttu-id="5123c-104">Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="5123c-104">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>

## <a name="syntax"></a><span data-ttu-id="5123c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5123c-105">Syntax</span></span>

```cpp
HRESULT _AxlPublicKeyBlobToPublicKeyToken (
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,
    [out] LPWSTR                 *ppwszPublicKeyToken
);
```

## <a name="parameters"></a><span data-ttu-id="5123c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5123c-106">Parameters</span></span>

 `pCspPublicKeyBlob`\
 <span data-ttu-id="5123c-107">[in] Blob de clave pública CSP.</span><span class="sxs-lookup"><span data-stu-id="5123c-107">[in] The CSP public key blob.</span></span>

 `ppwszPublicKeyHash`\
 <span data-ttu-id="5123c-108">[out] Puntero a WCHAR \* para recibir el hash de clave pública de codificación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="5123c-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>

## <a name="return-value"></a><span data-ttu-id="5123c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5123c-109">Return Value</span></span>

 <span data-ttu-id="5123c-110">`S_OK` si la función se realiza correctamente; de lo contrario es `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="5123c-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>

## <a name="requirements"></a><span data-ttu-id="5123c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5123c-111">Requirements</span></span>

<span data-ttu-id="5123c-112">**Ensamblado**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="5123c-112">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="5123c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5123c-113">See also</span></span>

- [<span data-ttu-id="5123c-114">Authenticode</span><span class="sxs-lookup"><span data-stu-id="5123c-114">Authenticode</span></span>](index.md)
