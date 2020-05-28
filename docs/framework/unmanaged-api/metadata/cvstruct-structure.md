---
title: CVStruct (Estructura)
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: 84791eba7c95d3278bd4650bd7d660e98fcb79d8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008929"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="20d1d-102">CVStruct (Estructura)</span><span class="sxs-lookup"><span data-stu-id="20d1d-102">CVStruct Structure</span></span>
<span data-ttu-id="20d1d-103">Contiene información que se utiliza al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="20d1d-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20d1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20d1d-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="20d1d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="20d1d-105">Members</span></span>  
  
|<span data-ttu-id="20d1d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="20d1d-106">Member</span></span>|<span data-ttu-id="20d1d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="20d1d-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="20d1d-108">Principal</span><span class="sxs-lookup"><span data-stu-id="20d1d-108">Major</span></span>|<span data-ttu-id="20d1d-109">Número de compilación de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="20d1d-109">Major version build number.</span></span>|  
|<span data-ttu-id="20d1d-110">Minor</span><span class="sxs-lookup"><span data-stu-id="20d1d-110">Minor</span></span>|<span data-ttu-id="20d1d-111">Número de compilación de la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="20d1d-111">Minor version build number.</span></span>|  
|<span data-ttu-id="20d1d-112">Sub</span><span class="sxs-lookup"><span data-stu-id="20d1d-112">Sub</span></span>|<span data-ttu-id="20d1d-113">Número de subcompilación.</span><span class="sxs-lookup"><span data-stu-id="20d1d-113">Sub-build number.</span></span>|  
|<span data-ttu-id="20d1d-114">Build</span><span class="sxs-lookup"><span data-stu-id="20d1d-114">Build</span></span>|<span data-ttu-id="20d1d-115">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="20d1d-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20d1d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20d1d-116">Requirements</span></span>  
 <span data-ttu-id="20d1d-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20d1d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20d1d-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="20d1d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20d1d-119">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="20d1d-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20d1d-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20d1d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d1d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20d1d-121">See also</span></span>

- [<span data-ttu-id="20d1d-122">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="20d1d-122">Metadata Structures</span></span>](metadata-structures.md)
