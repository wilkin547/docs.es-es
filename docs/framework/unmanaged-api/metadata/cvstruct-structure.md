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
ms.openlocfilehash: fb73980faa64464c572945fe5ad04e015dc8805b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720657"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="b7d2f-102">CVStruct (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b7d2f-102">CVStruct Structure</span></span>
<span data-ttu-id="b7d2f-103">Contiene información que se utiliza al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="b7d2f-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7d2f-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="b7d2f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b7d2f-105">Members</span></span>  
  
|<span data-ttu-id="b7d2f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b7d2f-106">Member</span></span>|<span data-ttu-id="b7d2f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7d2f-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b7d2f-108">Major</span><span class="sxs-lookup"><span data-stu-id="b7d2f-108">Major</span></span>|<span data-ttu-id="b7d2f-109">Número de compilación de versión principal.</span><span class="sxs-lookup"><span data-stu-id="b7d2f-109">Major version build number.</span></span>|  
|<span data-ttu-id="b7d2f-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b7d2f-110">Minor</span></span>|<span data-ttu-id="b7d2f-111">Número de compilación de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="b7d2f-111">Minor version build number.</span></span>|  
|<span data-ttu-id="b7d2f-112">Sub</span><span class="sxs-lookup"><span data-stu-id="b7d2f-112">Sub</span></span>|<span data-ttu-id="b7d2f-113">Número de compilación secundaria.</span><span class="sxs-lookup"><span data-stu-id="b7d2f-113">Sub-build number.</span></span>|  
|<span data-ttu-id="b7d2f-114">Compilar</span><span class="sxs-lookup"><span data-stu-id="b7d2f-114">Build</span></span>|<span data-ttu-id="b7d2f-115">número de compilación.</span><span class="sxs-lookup"><span data-stu-id="b7d2f-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7d2f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7d2f-116">Requirements</span></span>  
 <span data-ttu-id="b7d2f-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d2f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d2f-118">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7d2f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7d2f-119">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7d2f-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7d2f-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d2f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d2f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7d2f-121">See also</span></span>
- [<span data-ttu-id="b7d2f-122">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="b7d2f-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
