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
ms.openlocfilehash: 41e79a4c9587e3e738039cbf6a84087a2e7fc9b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741954"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll (Función)
Busca y carga el archivo DLL de mensaje. Devuelve 0 si el archivo DLL de mensaje no se pudo se encuentra o cargado. Debe ser el archivo DLL de mensaje en un subdirectorio cuyo nombre es un identificador de idioma, o en el directorio actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** alink.h  
  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Vea también

- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
