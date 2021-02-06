---
description: 'Más información acerca de: Getalinkmessagedll ((función)'
title: GetALinkMessageDll (Función)
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 67a294d1f21f50cee938ddeb14d1f30b4ccf911b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637877"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="06520-103">GetALinkMessageDll (Función)</span><span class="sxs-lookup"><span data-stu-id="06520-103">GetALinkMessageDll Function</span></span>

<span data-ttu-id="06520-104">Busca y carga el archivo DLL del mensaje.</span><span class="sxs-lookup"><span data-stu-id="06520-104">Finds and loads the message DLL.</span></span> <span data-ttu-id="06520-105">Devuelve 0 si el archivo DLL del mensaje no se pudo encontrar o cargar.</span><span class="sxs-lookup"><span data-stu-id="06520-105">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="06520-106">El archivo DLL del mensaje debe estar en un subdirectorio cuyo nombre sea un identificador de idioma o en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="06520-106">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06520-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06520-107">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="06520-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06520-108">Requirements</span></span>  

 <span data-ttu-id="06520-109">**Encabezado:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="06520-109">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="06520-110">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="06520-110">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06520-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="06520-111">See also</span></span>

- [<span data-ttu-id="06520-112">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="06520-112">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
