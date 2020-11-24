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
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll (Función)

Busca y carga el archivo DLL del mensaje. Devuelve 0 si el archivo DLL del mensaje no se pudo encontrar o cargar. El archivo DLL del mensaje debe estar en un subdirectorio cuyo nombre sea un identificador de idioma o en el directorio actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ALink. h  
  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Consulte también

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
