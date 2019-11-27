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
ms.openlocfilehash: 4c819bff50e6644a733374e9863d670d3323ee68
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449523"
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
  
## <a name="parameters"></a>Parámetros  
 `phEnum`  
 [in, out] Puntero al enumerador.  
  
 `td`  
 de El token de la definición de tipo cuyos tokens de MethodDef representan implementaciones de interfaz se van a enumerar.  
  
 `rImpls`  
 enuncia Matriz utilizada para almacenar los tokens de MethodDef.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rImpls`.  
  
 `pcImpls`  
 enuncia Número real de tokens devueltos en `rImpls`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` devolvió correctamente.|  
|`S_FALSE`|No hay tokens de MethodDef que enumerar. En ese caso, `pcImpls` se establece en cero.|  

## <a name="remarks"></a>Comentarios

La enumeración devuelve una colección de tokens de `mdInterfaceImpl` para cada interfaz implementada por el `TypeDef`especificado. Los tokens de interfaz se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps`). Las propiedades de los tokens de `mdInterfaceImpl` devueltos se pueden consultar mediante [getinterfaceimplprops (](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
