---
description: 'Más información acerca de: Createalink ((función)'
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
ms.openlocfilehash: cf34ae8d38a8339f539c770df8f5dd14e4a3e4b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638371"
---
# <a name="createalink-function"></a><span data-ttu-id="63947-103">CreateALink (Función)</span><span class="sxs-lookup"><span data-stu-id="63947-103">CreateALink Function</span></span>

<span data-ttu-id="63947-104">Crea una instancia del enlazador de ensamblado y establece un puntero a la interfaz especificada.</span><span class="sxs-lookup"><span data-stu-id="63947-104">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63947-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63947-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63947-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63947-106">Parameters</span></span>  
  
|<span data-ttu-id="63947-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="63947-107">Parameter</span></span>|<span data-ttu-id="63947-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="63947-108">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="63947-109">El nombre físico de una de las interfaces del enlazador de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="63947-109">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="63947-110">La ubicación en la que se completó correctamente contiene un puntero a la `riid` interfaz.</span><span class="sxs-lookup"><span data-stu-id="63947-110">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63947-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63947-111">Requirements</span></span>  

 <span data-ttu-id="63947-112">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="63947-112">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63947-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="63947-113">See also</span></span>

- [<span data-ttu-id="63947-114">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="63947-114">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
