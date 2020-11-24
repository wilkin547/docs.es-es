---
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
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684751"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="50da3-102">GetALinkMessageDll (Función)</span><span class="sxs-lookup"><span data-stu-id="50da3-102">GetALinkMessageDll Function</span></span>

<span data-ttu-id="50da3-103">Busca y carga el archivo DLL del mensaje.</span><span class="sxs-lookup"><span data-stu-id="50da3-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="50da3-104">Devuelve 0 si el archivo DLL del mensaje no se pudo encontrar o cargar.</span><span class="sxs-lookup"><span data-stu-id="50da3-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="50da3-105">El archivo DLL del mensaje debe estar en un subdirectorio cuyo nombre sea un identificador de idioma o en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="50da3-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50da3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50da3-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="50da3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50da3-107">Requirements</span></span>  

 <span data-ttu-id="50da3-108">**Encabezado:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="50da3-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="50da3-109">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="50da3-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50da3-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50da3-110">See also</span></span>

- [<span data-ttu-id="50da3-111">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="50da3-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
