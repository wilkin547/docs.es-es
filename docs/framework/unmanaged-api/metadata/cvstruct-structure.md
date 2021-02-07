---
description: 'Más información acerca de: estructura Cvstruct ('
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
ms.openlocfilehash: 25e8073f75620bca0737b11499d318cd57d6101c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707220"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="34e7c-103">CVStruct (Estructura)</span><span class="sxs-lookup"><span data-stu-id="34e7c-103">CVStruct Structure</span></span>

<span data-ttu-id="34e7c-104">Contiene información que se utiliza al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="34e7c-104">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e7c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34e7c-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="34e7c-106">Members</span><span class="sxs-lookup"><span data-stu-id="34e7c-106">Members</span></span>  
  
|<span data-ttu-id="34e7c-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="34e7c-107">Member</span></span>|<span data-ttu-id="34e7c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="34e7c-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="34e7c-109">Principal</span><span class="sxs-lookup"><span data-stu-id="34e7c-109">Major</span></span>|<span data-ttu-id="34e7c-110">Número de compilación de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="34e7c-110">Major version build number.</span></span>|  
|<span data-ttu-id="34e7c-111">Minor</span><span class="sxs-lookup"><span data-stu-id="34e7c-111">Minor</span></span>|<span data-ttu-id="34e7c-112">Número de compilación de la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="34e7c-112">Minor version build number.</span></span>|  
|<span data-ttu-id="34e7c-113">Sub</span><span class="sxs-lookup"><span data-stu-id="34e7c-113">Sub</span></span>|<span data-ttu-id="34e7c-114">Número de subcompilación.</span><span class="sxs-lookup"><span data-stu-id="34e7c-114">Sub-build number.</span></span>|  
|<span data-ttu-id="34e7c-115">Build</span><span class="sxs-lookup"><span data-stu-id="34e7c-115">Build</span></span>|<span data-ttu-id="34e7c-116">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="34e7c-116">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34e7c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34e7c-117">Requirements</span></span>  

 <span data-ttu-id="34e7c-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34e7c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34e7c-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="34e7c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34e7c-120">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34e7c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34e7c-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34e7c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e7c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="34e7c-122">See also</span></span>

- [<span data-ttu-id="34e7c-123">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="34e7c-123">Metadata Structures</span></span>](metadata-structures.md)
