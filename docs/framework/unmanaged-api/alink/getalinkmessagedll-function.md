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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 632f19e0ead57d5508265fece578bb22f18ba54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722730"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="ec7d1-102">GetALinkMessageDll (Función)</span><span class="sxs-lookup"><span data-stu-id="ec7d1-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="ec7d1-103">Busca y carga el archivo DLL de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec7d1-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="ec7d1-104">Devuelve 0 si el archivo DLL de mensaje no se pudo se encuentra o cargado.</span><span class="sxs-lookup"><span data-stu-id="ec7d1-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="ec7d1-105">Debe ser el archivo DLL de mensaje en un subdirectorio cuyo nombre es un identificador de idioma, o en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ec7d1-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7d1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec7d1-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="ec7d1-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec7d1-107">Requirements</span></span>  
 <span data-ttu-id="ec7d1-108">**Encabezado:** alink.h</span><span class="sxs-lookup"><span data-stu-id="ec7d1-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="ec7d1-109">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="ec7d1-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7d1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec7d1-110">See also</span></span>
- [<span data-ttu-id="ec7d1-111">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="ec7d1-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
