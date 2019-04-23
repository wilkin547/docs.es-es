---
title: CreateALink (Función)
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115627"
---
# <a name="createalink-function"></a><span data-ttu-id="a8793-102">CreateALink (Función)</span><span class="sxs-lookup"><span data-stu-id="a8793-102">CreateALink Function</span></span>
<span data-ttu-id="a8793-103">Crea una instancia de la herramienta Assembly Linker y establece un puntero a la interfaz especificada.</span><span class="sxs-lookup"><span data-stu-id="a8793-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8793-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8793-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8793-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8793-105">Parameters</span></span>  
  
|<span data-ttu-id="a8793-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a8793-106">Parameter</span></span>|<span data-ttu-id="a8793-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8793-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="a8793-108">El nombre físico de una de las interfaces de Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="a8793-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="a8793-109">La ubicación que se completa correctamente, contiene un puntero a la `riid` interfaz.</span><span class="sxs-lookup"><span data-stu-id="a8793-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8793-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8793-110">Requirements</span></span>  
 <span data-ttu-id="a8793-111">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="a8793-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8793-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8793-112">See also</span></span>

- [<span data-ttu-id="a8793-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="a8793-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
