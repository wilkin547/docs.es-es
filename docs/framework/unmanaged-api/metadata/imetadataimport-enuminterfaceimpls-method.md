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
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338065"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls (Método)
Enumera todas las interfaces implementadas por el `TypeDef`especificado. 
  
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
  
## <a name="parameters"></a>Parameters  
 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `td`  
 de El token de la definición de tipo cuyos tokens de MethodDef representan implementaciones de interfaz se van a enumerar.  
  
 `rImpls`  
 enuncia Matriz utilizada para almacenar los tokens de MethodDef.  
  
 `cMax`  
 de Longitud máxima de la matriz de `rImpls`.  
  
 `pcImpls`  
 enuncia Número real de tokens devueltos en `rImpls`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` devolvió correctamente.|  
|`S_FALSE`|No hay tokens de MethodDef que enumerar. En ese caso, `pcImpls` se establece en cero.|  

## <a name="remarks"></a>Notas

La enumeración devuelve una colección de tokens de `mdInterfaceImpl` para cada interfaz implementada por el `TypeDef`especificado. Los tokens de interfaz se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps`). Las propiedades de los tokens de `mdInterfaceImpl` devueltos se pueden consultar mediante [getinterfaceimplprops (](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
