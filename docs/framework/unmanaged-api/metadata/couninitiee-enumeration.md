---
title: COUNINITIEE (Enumeración)
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: 14942680a79c4d1fcc69092a4f752738db1fb0b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008926"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="d8a13-102">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a13-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="d8a13-103">Especifica las constantes utilizadas por [CoUninitializeEE (](../hosting/couninitializeee-function.md) al inicializar el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d8a13-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8a13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8a13-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="d8a13-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d8a13-105">Members</span></span>  
  
|<span data-ttu-id="d8a13-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d8a13-106">Member</span></span>|<span data-ttu-id="d8a13-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8a13-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="d8a13-108">Indica el modo de no inicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d8a13-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="d8a13-109">Indica el modo de anulación de la carga de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8a13-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8a13-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8a13-110">Requirements</span></span>  
 <span data-ttu-id="d8a13-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8a13-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8a13-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d8a13-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8a13-113">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d8a13-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8a13-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8a13-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a13-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8a13-115">See also</span></span>

- [<span data-ttu-id="d8a13-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="d8a13-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
