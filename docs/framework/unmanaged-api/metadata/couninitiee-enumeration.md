---
description: 'Más información sobre: enumeración COUNINITIEE ('
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
ms.openlocfilehash: 893ab96851e9c762a888f3c4cac98b486a0b4614
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707239"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="72241-103">COUNINITIEE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="72241-103">COUNINITIEE Enumeration</span></span>

<span data-ttu-id="72241-104">Especifica las constantes utilizadas por [CoUninitializeEE (](../hosting/couninitializeee-function.md) al inicializar el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="72241-104">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72241-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72241-105">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="72241-106">Members</span><span class="sxs-lookup"><span data-stu-id="72241-106">Members</span></span>  
  
|<span data-ttu-id="72241-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="72241-107">Member</span></span>|<span data-ttu-id="72241-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="72241-108">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="72241-109">Indica el modo de no inicialización predeterminado.</span><span class="sxs-lookup"><span data-stu-id="72241-109">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="72241-110">Indica el modo de anulación de la carga de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="72241-110">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72241-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72241-111">Requirements</span></span>  

 <span data-ttu-id="72241-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72241-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72241-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="72241-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72241-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72241-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72241-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72241-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72241-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="72241-116">See also</span></span>

- [<span data-ttu-id="72241-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="72241-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
