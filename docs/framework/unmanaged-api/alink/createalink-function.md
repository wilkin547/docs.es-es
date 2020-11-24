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
ms.openlocfilehash: 98c6ed4657dc69554a9fcca27145f65c621492f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683736"
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
|`ppInterface`|La ubicación en la que se completó correctamente contiene un puntero a la `riid` interfaz.|  
  
## <a name="requirements"></a>Requisitos  

 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Consulte también

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
