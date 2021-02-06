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
  
## <a name="see-also"></a>Vea también

- [Al.exe (Assembly Linker)](../../tools/al-exe-assembly-linker.md)
