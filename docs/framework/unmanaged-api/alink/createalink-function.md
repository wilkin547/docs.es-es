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
ms.openlocfilehash: 98c6ed4657dc69554a9fcca27145f65c621492f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683736"
---
# <a name="createalink-function"></a><span data-ttu-id="0970d-102">CreateALink (Función)</span><span class="sxs-lookup"><span data-stu-id="0970d-102">CreateALink Function</span></span>

<span data-ttu-id="0970d-103">Crea una instancia del enlazador de ensamblado y establece un puntero a la interfaz especificada.</span><span class="sxs-lookup"><span data-stu-id="0970d-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0970d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0970d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0970d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0970d-105">Parameters</span></span>  
  
|<span data-ttu-id="0970d-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0970d-106">Parameter</span></span>|<span data-ttu-id="0970d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0970d-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="0970d-108">El nombre físico de una de las interfaces del enlazador de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0970d-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="0970d-109">La ubicación en la que se completó correctamente contiene un puntero a la `riid` interfaz.</span><span class="sxs-lookup"><span data-stu-id="0970d-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0970d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0970d-110">Requirements</span></span>  

 <span data-ttu-id="0970d-111">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="0970d-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0970d-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0970d-112">See also</span></span>

- [<span data-ttu-id="0970d-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="0970d-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
