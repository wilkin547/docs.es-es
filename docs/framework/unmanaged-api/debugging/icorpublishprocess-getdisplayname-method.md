---
description: 'Más información acerca de: ICorPublishProcess:: GetDisplayName (método)'
title: ICorPublishProcess::GetDisplayName (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: 7aef55a40c24953766377f21e8291bceb1594480
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794590"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="959df-103">ICorPublishProcess::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="959df-103">ICorPublishProcess::GetDisplayName Method</span></span>

<span data-ttu-id="959df-104">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="959df-104">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="959df-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="959df-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="959df-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="959df-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="959df-107">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="959df-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="959df-108">enuncia Número de caracteres anchos devueltos en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="959df-108">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="959df-109">enuncia Una matriz para almacenar el nombre, incluida la ruta de acceso completa, del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="959df-109">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="959df-110">El nombre termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="959df-110">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="959df-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="959df-111">Requirements</span></span>  

 <span data-ttu-id="959df-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="959df-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="959df-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="959df-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="959df-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="959df-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="959df-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="959df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959df-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="959df-116">See also</span></span>

- [<span data-ttu-id="959df-117">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="959df-117">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
