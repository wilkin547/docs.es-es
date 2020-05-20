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
ms.openlocfilehash: dc76274d3b0acbbe0b03eb141d2b3e6ff9063afb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421129"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="9e6e0-102">ICorPublishProcess::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="9e6e0-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="9e6e0-103">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9e6e0-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e6e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e6e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e6e0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e6e0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9e6e0-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="9e6e0-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9e6e0-107">enuncia Número de caracteres anchos devueltos en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="9e6e0-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="9e6e0-108">enuncia Una matriz para almacenar el nombre, incluida la ruta de acceso completa, del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="9e6e0-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="9e6e0-109">El nombre termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="9e6e0-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e6e0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e6e0-110">Requirements</span></span>  
 <span data-ttu-id="9e6e0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e6e0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e6e0-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="9e6e0-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9e6e0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e6e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e6e0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e6e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6e0-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9e6e0-115">See also</span></span>

- [<span data-ttu-id="9e6e0-116">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e6e0-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
