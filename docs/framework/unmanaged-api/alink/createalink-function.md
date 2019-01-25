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
ms.openlocfilehash: f809395de68b596f769f9396da8668bf296b1aa2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675046"
---
# <a name="createalink-function"></a><span data-ttu-id="ea355-102">CreateALink (Función)</span><span class="sxs-lookup"><span data-stu-id="ea355-102">CreateALink Function</span></span>
<span data-ttu-id="ea355-103">Crea una instancia de la herramienta Assembly Linker y establece un puntero a la interfaz especificada.</span><span class="sxs-lookup"><span data-stu-id="ea355-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea355-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea355-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea355-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea355-105">Parameters</span></span>  
  
|<span data-ttu-id="ea355-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ea355-106">Parameter</span></span>|<span data-ttu-id="ea355-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea355-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="ea355-108">El nombre físico de una de las interfaces de Assembly Linker.</span><span class="sxs-lookup"><span data-stu-id="ea355-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="ea355-109">La ubicación que se completa correctamente, contiene un puntero a la `riid` interfaz.</span><span class="sxs-lookup"><span data-stu-id="ea355-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea355-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea355-110">Requirements</span></span>  
 <span data-ttu-id="ea355-111">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="ea355-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea355-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea355-112">See also</span></span>
- [<span data-ttu-id="ea355-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="ea355-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
