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
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449347"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll (Función)
Busca y carga el archivo DLL del mensaje. Devuelve 0 si el archivo DLL del mensaje no se pudo encontrar o cargar. El archivo DLL del mensaje debe estar en un subdirectorio cuyo nombre sea un identificador de idioma o en el directorio actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** ALink. h  
  
 **Biblioteca**: ALink. dll  
  
## <a name="see-also"></a>Vea también

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
