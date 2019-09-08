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
ms.openlocfilehash: 24f7e2d5a547b78ceb4808feaf581c6f49807cf7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787618"
---
# <a name="createalink-function"></a><span data-ttu-id="a548a-102">CreateALink (Función)</span><span class="sxs-lookup"><span data-stu-id="a548a-102">CreateALink Function</span></span>
<span data-ttu-id="a548a-103">Crea una instancia del enlazador de ensamblado y establece un puntero a la interfaz especificada.</span><span class="sxs-lookup"><span data-stu-id="a548a-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a548a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a548a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a548a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a548a-105">Parameters</span></span>  
  
|<span data-ttu-id="a548a-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a548a-106">Parameter</span></span>|<span data-ttu-id="a548a-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a548a-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="a548a-108">El nombre físico de una de las interfaces del enlazador de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a548a-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="a548a-109">La ubicación en la que se completó correctamente contiene un `riid` puntero a la interfaz.</span><span class="sxs-lookup"><span data-stu-id="a548a-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a548a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a548a-110">Requirements</span></span>  
 <span data-ttu-id="a548a-111">**Biblioteca**: ALink. dll</span><span class="sxs-lookup"><span data-stu-id="a548a-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a548a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a548a-112">See also</span></span>

- [<span data-ttu-id="a548a-113">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="a548a-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
