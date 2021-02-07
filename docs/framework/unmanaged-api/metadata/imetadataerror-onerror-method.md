---
description: 'Más información sobre: Imetadataerror (:: OnError (método)'
title: IMetaDataError::OnError (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
ms.openlocfilehash: 9556f1bd7758755d9160e3a2e91a1fe5786aa562
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670975"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="edb84-103">IMetaDataError::OnError (Método)</span><span class="sxs-lookup"><span data-stu-id="edb84-103">IMetaDataError::OnError Method</span></span>

<span data-ttu-id="edb84-104">Proporciona una notificación de los errores que se producen durante la combinación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="edb84-104">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb84-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edb84-105">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edb84-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="edb84-106">Parameters</span></span>  

 `hrError`  
 <span data-ttu-id="edb84-107">de El valor de error HRESULT devuelto al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="edb84-107">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="edb84-108">de Token de metadatos del objeto de código que se estaba combinando cuando se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="edb84-108">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edb84-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edb84-109">Requirements</span></span>  

 <span data-ttu-id="edb84-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edb84-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edb84-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="edb84-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edb84-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="edb84-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="edb84-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edb84-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb84-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="edb84-114">See also</span></span>

- [<span data-ttu-id="edb84-115">IMetaDataError (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edb84-115">IMetaDataError Interface</span></span>](imetadataerror-interface.md)
