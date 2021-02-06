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
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll (Función)

Busca y carga el archivo DLL del mensaje. Devuelve 0 si el archivo DLL del mensaje no se pudo encontrar o cargar. El archivo DLL del mensaje debe estar en un subdirectorio cuyo nombre sea un identificador de idioma o en el directorio actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** ALink. h  
  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Vea también

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
