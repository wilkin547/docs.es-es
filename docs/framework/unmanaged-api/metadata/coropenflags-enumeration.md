---
title: CorOpenFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c08b1f6be41de63886115e5aed6bcad901658bb5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509225"
---
# <a name="coropenflags-enumeration"></a>CorOpenFlags (Enumeración)
Contiene valores de marca que controlan el comportamiento de los metadatos al abrir archivos de manifiesto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ofRead`|Indica que el archivo se debe abrir solo para lectura.|  
|`ofWrite`|Indica que el archivo se debe abrir para escritura.<br /><br /> Si usa la marca `ofWrite` al abrir un archivo .winmd, debe pasar también la marca `ofNoTransform`.|  
|`ofReadWriteMask`|Máscara para lectura y escritura.|  
|`ofCopyMemory`|Indica que el archivo se debe leer en la memoria. Los metadatos deben mantener su propia copia.|  
|`ofCacheImage`|Obsoleto. Esta marca se omite.|  
|`ofManifestMetadata`|Obsoleto. Esta marca se omite.|  
|`ofReadOnly`|Indica que se debe abrir el archivo para lectura y que una llamada a `QueryInterface` para un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) no se puede realizar.|  
|`ofTakeOwnership`|Indica que la memoria se asignó mediante una llamada a [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) y se liberarán los metadatos.|  
|`ofNoTypeLib`|Obsoleto. Esta marca se omite.|  
|`ofNoTransform`|Indica que se deben deshabilitar las transformaciones automáticas de archivos .winmd. En otras palabras, se debe deshabilitar la proyección de un tipo de Windows Runtime en un tipo de .NET Framework. Para obtener más información, consulte [debajo de la directiva el interior de .NET y el tiempo de ejecución de Windows](https://msdn.microsoft.com/magazine/jj651569.aspx).|  
|`ofReserved1`|Reservado para uso interno.|  
|`ofReserved2`|Reservado para uso interno.|  
|`ofReserved`|Reservado para uso interno.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
