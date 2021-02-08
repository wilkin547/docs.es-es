---
description: 'Más información acerca de: ICLRDataTarget:: Getimagebase ((método)'
title: ICLRDataTarget::GetImageBase (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: 34e8341b219aaa184b4894c631f854e0a31921d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794876"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="09dd0-103">ICLRDataTarget::GetImageBase (Método)</span><span class="sxs-lookup"><span data-stu-id="09dd0-103">ICLRDataTarget::GetImageBase Method</span></span>

<span data-ttu-id="09dd0-104">Obtiene la dirección de memoria base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="09dd0-104">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09dd0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09dd0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09dd0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09dd0-106">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="09dd0-107">de Nombre de archivo de la imagen, incluida su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="09dd0-107">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="09dd0-108">enuncia Puntero a un CLRDATA_ADDRESS que almacena la dirección base de la imagen.</span><span class="sxs-lookup"><span data-stu-id="09dd0-108">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09dd0-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="09dd0-109">Remarks</span></span>  

 <span data-ttu-id="09dd0-110">El nombre del archivo de imagen puede tener o no una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="09dd0-110">The image file name may or may not have a path.</span></span> <span data-ttu-id="09dd0-111">Si se especifica una ruta de acceso, la coincidencia se realiza en toda la ruta de acceso; de lo contrario, la búsqueda de coincidencias se realiza solo en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="09dd0-111">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09dd0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09dd0-112">Requirements</span></span>  

 <span data-ttu-id="09dd0-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09dd0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09dd0-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="09dd0-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="09dd0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09dd0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09dd0-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09dd0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09dd0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="09dd0-117">See also</span></span>

- [<span data-ttu-id="09dd0-118">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09dd0-118">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
