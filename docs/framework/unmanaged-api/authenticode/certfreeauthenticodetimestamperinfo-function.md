---
description: 'Más información acerca de: Certfreeauthenticodetimestamperinfo ((función)'
title: CertFreeAuthenticodeTimestamperInfo (Función)
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
topic_type:
- apiref
ms.openlocfilehash: 5234a90ea1d0272a7409b1b0b4def2160b77a513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772944"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="0f822-103">CertFreeAuthenticodeTimestamperInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="0f822-103">CertFreeAuthenticodeTimestamperInfo Function</span></span>

<span data-ttu-id="0f822-104">Libera los recursos asignados para la estructura de [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="0f822-104">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f822-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f822-105">Syntax</span></span>

```cpp
HRESULT CertFreeAuthenticodeTimestamperInfo (
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo
);
```

## <a name="parameters"></a><span data-ttu-id="0f822-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f822-106">Parameters</span></span>

 `pTimestamperInfo`\
 <span data-ttu-id="0f822-107">[in, out] Información sobre la marca de tiempo que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="0f822-107">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="0f822-108">Vea la estructura [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="0f822-108">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>

## <a name="return-value"></a><span data-ttu-id="0f822-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f822-109">Return Value</span></span>

 <span data-ttu-id="0f822-110">`S_OK` si la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f822-110">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="0f822-111">De lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="0f822-111">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f822-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f822-112">Requirements</span></span>

<span data-ttu-id="0f822-113">**Ensamblado**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="0f822-113">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="0f822-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f822-114">See also</span></span>

- [<span data-ttu-id="0f822-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="0f822-115">Authenticode</span></span>](index.md)
