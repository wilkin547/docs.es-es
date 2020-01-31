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
ms.openlocfilehash: 7f2e644340a2ec7fe807830422b927ce811ddcf9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790573"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="191a8-102">ICorPublishProcess::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="191a8-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="191a8-103">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="191a8-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="191a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="191a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="191a8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="191a8-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="191a8-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="191a8-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="191a8-107">enuncia Número de caracteres anchos devueltos en la matriz de `szName`.</span><span class="sxs-lookup"><span data-stu-id="191a8-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="191a8-108">enuncia Una matriz para almacenar el nombre, incluida la ruta de acceso completa, del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="191a8-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="191a8-109">El nombre termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="191a8-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="191a8-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="191a8-110">Requirements</span></span>  
 <span data-ttu-id="191a8-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="191a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="191a8-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="191a8-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="191a8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="191a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="191a8-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="191a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191a8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="191a8-115">See also</span></span>

- [<span data-ttu-id="191a8-116">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="191a8-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
