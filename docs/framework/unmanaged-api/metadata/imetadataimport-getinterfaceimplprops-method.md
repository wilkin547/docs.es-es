---
description: 'Más información sobre: IMetaDataImport:: Getinterfaceimplprops ((método)'
title: IMetaDataImport::GetInterfaceImplProps (Método)
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: 6b3c9394bcf37f700c84e1fda0b785dc0c3f4713
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783916"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps (Método)

Obtiene un puntero a los tokens de metadatos para el <xref:System.Type> que implementa el método especificado y para la interfaz que declara ese método.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `iiImpl`  
 de Token de metadatos que representa el método para el que se van a devolver los tokens de la clase y la interfaz.  
  
 `pClass`  
 enuncia Token de metadatos que representa la clase que implementa el método.  
  
 `ptkIface`  
 enuncia Token de metadatos que representa la interfaz que define el método implementado.  

## <a name="remarks"></a>Observaciones

 Para obtener el valor de `iImpl` , se llama al método [enuminterfaceimpls (](imetadataimport-enuminterfaceimpls-method.md) .

 Por ejemplo, supongamos que una clase tiene un `mdTypeDef` valor de token de 0x02000007 y que implementa tres interfaces cuyos tipos tienen tokens:

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

Conceptualmente, esta información se almacena en una tabla de implementación de interfaz como:

| Número de fila. | Token de clase | Token de interfaz |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Recuerde que el token es un valor de 4 bytes:

- Los 3 bytes inferiores contienen el número de fila o RID.
- El byte superior contiene el tipo de token – 0x09 para `mdtInterfaceImpl` .

`GetInterfaceImplProps` Devuelve la información contenida en la fila cuyo token se proporciona en el `iImpl` argumento.
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
