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
ms.openlocfilehash: 77e801b048709949c384f642fc0d0ecb5d7eb512
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178382"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="29bb8-102">ICorPublishProcess::GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="29bb8-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="29bb8-103">Obtiene la ruta de acceso completa del ejecutable para el proceso al que hace referencia este [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="29bb8-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29bb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29bb8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29bb8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29bb8-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="29bb8-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="29bb8-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="29bb8-107">[fuera] El número de caracteres `szName` anchos devueltos en la matriz.</span><span class="sxs-lookup"><span data-stu-id="29bb8-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="29bb8-108">[fuera] Matriz para almacenar el nombre, incluida la ruta de acceso completa, del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="29bb8-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="29bb8-109">El nombre es null-terminated.</span><span class="sxs-lookup"><span data-stu-id="29bb8-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29bb8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29bb8-110">Requirements</span></span>  
 <span data-ttu-id="29bb8-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29bb8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29bb8-112">**Encabezado:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="29bb8-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="29bb8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29bb8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29bb8-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29bb8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bb8-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29bb8-115">See also</span></span>

- [<span data-ttu-id="29bb8-116">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="29bb8-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
