---
description: 'Más información acerca de: Certfreeauthenticodesignerinfo ((función)'
title: CertFreeAuthenticodeSignerInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
topic_type:
- apiref
ms.openlocfilehash: 6e8a97e8fee37d885c7d32102ed8cc7654992223
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772983"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="d4149-103">CertFreeAuthenticodeSignerInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="d4149-103">CertFreeAuthenticodeSignerInfo Function</span></span>

<span data-ttu-id="d4149-104">Libera los recursos asignados para la estructura de [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d4149-104">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4149-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4149-105">Syntax</span></span>

```cpp
HRESULT CertFreeAuthenticodeSignerInfo (
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);
```

## <a name="parameters"></a><span data-ttu-id="d4149-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4149-106">Parameters</span></span>

 `pSignerInfo`\
 <span data-ttu-id="d4149-107">[in, out] Información sobre el firmante que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="d4149-107">[in, out] Signer information to be released.</span></span> <span data-ttu-id="d4149-108">Vea la estructura [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d4149-108">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>

## <a name="return-value"></a><span data-ttu-id="d4149-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d4149-109">Return Value</span></span>

 <span data-ttu-id="d4149-110">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="d4149-110">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="d4149-111">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="d4149-111">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4149-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4149-112">Requirements</span></span>

<span data-ttu-id="d4149-113">**Ensamblado**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="d4149-113">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="d4149-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4149-114">See also</span></span>

- [<span data-ttu-id="d4149-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d4149-115">Authenticode</span></span>](index.md)
