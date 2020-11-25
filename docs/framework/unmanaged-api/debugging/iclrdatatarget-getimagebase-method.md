---
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
ms.openlocfilehash: f1b9f55a383f1deb867c6b3e2fa385a82158d1e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703582"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="87ca6-102">ICLRDataTarget::GetImageBase (Método)</span><span class="sxs-lookup"><span data-stu-id="87ca6-102">ICLRDataTarget::GetImageBase Method</span></span>

<span data-ttu-id="87ca6-103">Obtiene la dirección de memoria base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="87ca6-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87ca6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87ca6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87ca6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87ca6-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="87ca6-106">de Nombre de archivo de la imagen, incluida su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="87ca6-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="87ca6-107">enuncia Puntero a un CLRDATA_ADDRESS que almacena la dirección base de la imagen.</span><span class="sxs-lookup"><span data-stu-id="87ca6-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87ca6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87ca6-108">Remarks</span></span>  

 <span data-ttu-id="87ca6-109">El nombre del archivo de imagen puede tener o no una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="87ca6-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="87ca6-110">Si se especifica una ruta de acceso, la coincidencia se realiza en toda la ruta de acceso; de lo contrario, la búsqueda de coincidencias se realiza solo en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="87ca6-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87ca6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87ca6-111">Requirements</span></span>  

 <span data-ttu-id="87ca6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87ca6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87ca6-113">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="87ca6-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="87ca6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87ca6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87ca6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87ca6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ca6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87ca6-116">See also</span></span>

- [<span data-ttu-id="87ca6-117">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87ca6-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
