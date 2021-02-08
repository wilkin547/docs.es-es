---
description: 'Más información sobre: enumeración CorOpenFlags ('
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
ms.openlocfilehash: b8bc31b5c2b7ff0c7984aa92c38e96569b80d22e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784306"
---
# <a name="coropenflags-enumeration"></a>CorOpenFlags (Enumeración)

Contiene valores de marca que controlan el comportamiento de los metadatos al abrir archivos de manifiesto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ofRead`|Indica que el archivo se debe abrir solo para lectura.|  
|`ofWrite`|Indica que el archivo se debe abrir para escritura.<br /><br /> Si usa la marca `ofWrite` al abrir un archivo .winmd, debe pasar también la marca `ofNoTransform`.|  
|`ofReadWriteMask`|Máscara para lectura y escritura.|  
|`ofCopyMemory`|Indica que el archivo se debe leer en la memoria. Los metadatos deben mantener su propia copia.|  
|`ofCacheImage`|Obsoleto. Esta marca se omite.|  
|`ofManifestMetadata`|Obsoleto. Esta marca se omite.|  
|`ofReadOnly`|Indica que el archivo se debe abrir para lectura y que no se puede realizar una llamada a `QueryInterface` para [IMetaDataEmit](imetadataemit-interface.md) .|  
|`ofTakeOwnership`|Indica que la memoria se asignó mediante una llamada a [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) y que los metadatos liberarán.|  
|`ofNoTypeLib`|Obsoleto. Esta marca se omite.|  
|`ofNoTransform`|Indica que se deben deshabilitar las transformaciones automáticas de archivos .winmd. En otras palabras, se debe deshabilitar la proyección de un tipo de Windows Runtime en un tipo de .NET Framework. Para obtener más información, vea [Windows Runtime y CLR: debajo del capó con .net y el Windows Runtime](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).|  
|`ofReserved1`|Reservado para uso interno.|  
|`ofReserved2`|Reservado para uso interno.|  
|`ofReserved`|Reservado para uso interno.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
