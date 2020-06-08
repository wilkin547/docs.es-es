---
title: IMetaDataImport::EnumInterfaceImpls (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: 910c40413075131765a37e00703ac892e3f39641
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492252"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls (Método)
Enumera todas las interfaces implementadas por el especificado `TypeDef` .
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `td`  
 de El token de la definición de tipo cuyos tokens de MethodDef representan implementaciones de interfaz se van a enumerar.  
  
 `rImpls`  
 enuncia Matriz utilizada para almacenar los tokens de MethodDef.  
  
 `cMax`  
 de Longitud máxima de la `rImpls` matriz.  
  
 `pcImpls`  
 enuncia Número real de tokens devueltos en `rImpls` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls`se devolvió correctamente.|  
|`S_FALSE`|No hay tokens de MethodDef que enumerar. En ese caso, `pcImpls` se establece en cero.|  

## <a name="remarks"></a>Comentarios

La enumeración devuelve una colección de `mdInterfaceImpl` tokens para cada interfaz implementada por el especificado `TypeDef` . Los tokens de interfaz se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps` ). Las propiedades de los `mdInterfaceImpl` tokens devueltos se pueden consultar mediante [getinterfaceimplprops (](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
