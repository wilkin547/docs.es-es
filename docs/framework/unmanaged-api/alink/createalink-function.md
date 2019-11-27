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
ms.openlocfilehash: 9165a4db7e65fb0f409a902b06d32e9c2988aa69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446547"
---
# <a name="createalink-function"></a><span data-ttu-id="b945a-102">CreateALink (Función)</span><span class="sxs-lookup"><span data-stu-id="b945a-102">CreateALink Function</span></span>
<span data-ttu-id="b945a-103">Crea una instancia del enlazador de ensamblado y establece un puntero a la interfaz especificada.</span><span class="sxs-lookup"><span data-stu-id="b945a-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b945a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b945a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b945a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b945a-105">Parameters</span></span>  
  
|<span data-ttu-id="b945a-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b945a-106">Parameter</span></span>|<span data-ttu-id="b945a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b945a-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="b945a-108">El nombre físico de una de las interfaces del enlazador de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b945a-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="b945a-109">La ubicación en la que se completó correctamente contiene un puntero a la interfaz `riid`.</span><span class="sxs-lookup"><span data-stu-id="b945a-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b945a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b945a-110">Requirements</span></span>  
 <span data-ttu-id="b945a-111">**Biblioteca**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="b945a-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b945a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b945a-112">See also</span></span>

- [<span data-ttu-id="b945a-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="b945a-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
