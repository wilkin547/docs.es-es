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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 195f311d58f2169d715bb33986ee6e591622f377
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445048"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="eb599-102">CVStruct (Estructura)</span><span class="sxs-lookup"><span data-stu-id="eb599-102">CVStruct Structure</span></span>
<span data-ttu-id="eb599-103">Contiene información que se utiliza al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="eb599-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb599-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb599-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="eb599-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="eb599-105">Members</span></span>  
  
|<span data-ttu-id="eb599-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="eb599-106">Member</span></span>|<span data-ttu-id="eb599-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb599-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="eb599-108">Major</span><span class="sxs-lookup"><span data-stu-id="eb599-108">Major</span></span>|<span data-ttu-id="eb599-109">Número de compilación de versión principal.</span><span class="sxs-lookup"><span data-stu-id="eb599-109">Major version build number.</span></span>|  
|<span data-ttu-id="eb599-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="eb599-110">Minor</span></span>|<span data-ttu-id="eb599-111">Número de compilación de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="eb599-111">Minor version build number.</span></span>|  
|<span data-ttu-id="eb599-112">Sub</span><span class="sxs-lookup"><span data-stu-id="eb599-112">Sub</span></span>|<span data-ttu-id="eb599-113">Número de compilación secundaria.</span><span class="sxs-lookup"><span data-stu-id="eb599-113">Sub-build number.</span></span>|  
|<span data-ttu-id="eb599-114">Compilar</span><span class="sxs-lookup"><span data-stu-id="eb599-114">Build</span></span>|<span data-ttu-id="eb599-115">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="eb599-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb599-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb599-116">Requirements</span></span>  
 <span data-ttu-id="eb599-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb599-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb599-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb599-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb599-119">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb599-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb599-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb599-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb599-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb599-121">See Also</span></span>  
 [<span data-ttu-id="eb599-122">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="eb599-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
