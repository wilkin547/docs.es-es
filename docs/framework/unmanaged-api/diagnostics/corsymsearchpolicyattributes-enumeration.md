---
title: CorSymSearchPolicyAttributes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29766636cd151744d25cf66deb60cd2e066e1b32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775782"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>CorSymSearchPolicyAttributes (Enumeración)
Especifica la directiva que se usará al realizar una búsqueda de un lector de símbolos. Estas constantes se utilizan por el [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) y [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) métodos.  
  
> [!IMPORTANT]
>  Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`AllowRegistryAccess`|Consulta el registro para las rutas de búsqueda de símbolos.|  
|`AllowSymbolServerAccess`|Tiene acceso a un servidor de símbolos.|  
|`AllowOriginalPathAccess`|Busca la ruta de acceso especificada en el directorio de depuración.|  
|`AllowReferencePathAccess`|Busca el archivo PDB en el lugar donde está el archivo .exe.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
