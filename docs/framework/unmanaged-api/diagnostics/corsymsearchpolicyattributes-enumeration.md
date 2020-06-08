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
ms.openlocfilehash: 8af71314cf8a24c710d3b8980c082daaf9186715
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501877"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>CorSymSearchPolicyAttributes (Enumeración)
Especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos. Estas constantes las usan los métodos [isymunmanagedbinder2 (:: getreaderforfile2 (](isymunmanagedbinder2-getreaderforfile2-method.md) y [Isymunmanagedbinder3 (:: getreaderfromcallback (](isymunmanagedbinder3-getreaderfromcallback-method.md) .  
  
> [!IMPORTANT]
> Se trata de un riesgo para la seguridad de abrir un archivo de base de datos de programa (PDB) desde un origen que no es de confianza.  
  
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`AllowRegistryAccess`|Consulta el registro para buscar rutas de acceso de búsqueda de símbolos.|  
|`AllowSymbolServerAccess`|Obtiene acceso a un servidor de símbolos.|  
|`AllowOriginalPathAccess`|Busca la ruta de acceso especificada en el directorio de depuración.|  
|`AllowReferencePathAccess`|Busca el archivo PDB en el lugar donde está el archivo. exe.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también:

- [Enumeraciones de almacén de símbolos de diagnósticos](diagnostics-symbol-store-enumerations.md)
