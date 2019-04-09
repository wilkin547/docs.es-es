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
ms.openlocfilehash: 4a5f06b3f79fed5dac5a6f07650e4fabd0aa5867
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142173"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="ab45c-102">CVStruct (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ab45c-102">CVStruct Structure</span></span>
<span data-ttu-id="ab45c-103">Contiene información que se utiliza al instalar un módulo o una imagen compuesta.</span><span class="sxs-lookup"><span data-stu-id="ab45c-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab45c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab45c-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="ab45c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ab45c-105">Members</span></span>  
  
|<span data-ttu-id="ab45c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ab45c-106">Member</span></span>|<span data-ttu-id="ab45c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab45c-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ab45c-108">Major</span><span class="sxs-lookup"><span data-stu-id="ab45c-108">Major</span></span>|<span data-ttu-id="ab45c-109">Número de compilación de versión principal.</span><span class="sxs-lookup"><span data-stu-id="ab45c-109">Major version build number.</span></span>|  
|<span data-ttu-id="ab45c-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="ab45c-110">Minor</span></span>|<span data-ttu-id="ab45c-111">Número de compilación de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="ab45c-111">Minor version build number.</span></span>|  
|<span data-ttu-id="ab45c-112">Sub</span><span class="sxs-lookup"><span data-stu-id="ab45c-112">Sub</span></span>|<span data-ttu-id="ab45c-113">Número de compilación secundaria.</span><span class="sxs-lookup"><span data-stu-id="ab45c-113">Sub-build number.</span></span>|  
|<span data-ttu-id="ab45c-114">Compilar</span><span class="sxs-lookup"><span data-stu-id="ab45c-114">Build</span></span>|<span data-ttu-id="ab45c-115">número de compilación.</span><span class="sxs-lookup"><span data-stu-id="ab45c-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab45c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab45c-116">Requirements</span></span>  
 <span data-ttu-id="ab45c-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab45c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab45c-118">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ab45c-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab45c-119">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab45c-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ab45c-120">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ab45c-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab45c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab45c-121">See also</span></span>

- [<span data-ttu-id="ab45c-122">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="ab45c-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
