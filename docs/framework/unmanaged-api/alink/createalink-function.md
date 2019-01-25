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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f809395de68b596f769f9396da8668bf296b1aa2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675046"
---
# <a name="createalink-function"></a>CreateALink (Función)
Crea una instancia de la herramienta Assembly Linker y establece un puntero a la interfaz especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`riid`|El nombre físico de una de las interfaces de Assembly Linker.|  
|`ppInterface`|La ubicación que se completa correctamente, contiene un puntero a la `riid` interfaz.|  
  
## <a name="requirements"></a>Requisitos  
 **Biblioteca**: alink.dll  
  
## <a name="see-also"></a>Vea también
- [Al.exe (Assembly Linker)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
