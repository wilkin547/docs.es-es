---
description: 'Más información sobre: enumeración Corregflags ('
title: CorRegFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: 534b7b4b170d1f586e967807c4cc8a9c82648e8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753670"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="29102-103">CorRegFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="29102-103">CorRegFlags Enumeration</span></span>

<span data-ttu-id="29102-104">Proporciona valores de marca usados para el registro al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="29102-104">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29102-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29102-105">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="29102-106">Members</span><span class="sxs-lookup"><span data-stu-id="29102-106">Members</span></span>  
  
|<span data-ttu-id="29102-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="29102-107">Member</span></span>|<span data-ttu-id="29102-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="29102-108">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="29102-109">Especifica que los archivos no se deben copiar en el destino.</span><span class="sxs-lookup"><span data-stu-id="29102-109">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="29102-110">Especifica que el módulo o el compuesto es una configuración.</span><span class="sxs-lookup"><span data-stu-id="29102-110">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="29102-111">Especifica que el módulo o compuesto tiene referencias de clase.</span><span class="sxs-lookup"><span data-stu-id="29102-111">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29102-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29102-112">Requirements</span></span>  

 <span data-ttu-id="29102-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29102-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29102-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="29102-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29102-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29102-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="29102-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29102-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29102-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="29102-117">See also</span></span>

- [<span data-ttu-id="29102-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="29102-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
