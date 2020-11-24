---
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
ms.openlocfilehash: 5a037695892252042d7827165595f7bad0feba56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693169"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="4a1ed-102">ICorPublishProcess::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="4a1ed-102">ICorPublishProcess::GetDisplayName Method</span></span>

<span data-ttu-id="4a1ed-103">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4a1ed-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a1ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a1ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a1ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a1ed-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="4a1ed-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="4a1ed-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4a1ed-107">enuncia Número de caracteres anchos devueltos en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="4a1ed-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="4a1ed-108">enuncia Una matriz para almacenar el nombre, incluida la ruta de acceso completa, del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4a1ed-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="4a1ed-109">El nombre termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="4a1ed-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a1ed-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a1ed-110">Requirements</span></span>  

 <span data-ttu-id="4a1ed-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a1ed-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a1ed-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="4a1ed-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4a1ed-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a1ed-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a1ed-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a1ed-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a1ed-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a1ed-115">See also</span></span>

- [<span data-ttu-id="4a1ed-116">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a1ed-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
