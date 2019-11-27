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
# <a name="createalink-function"></a>CreateALink (Función)
Crea una instancia del enlazador de ensamblado y establece un puntero a la interfaz especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`riid`|El nombre físico de una de las interfaces del enlazador de ensamblados.|  
|`ppInterface`|La ubicación en la que se completó correctamente contiene un puntero a la interfaz `riid`.|  
  
## <a name="requirements"></a>Requisitos  
 **Biblioteca**: ALink. dll  
  
## <a name="see-also"></a>Vea también

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
