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
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175504"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a>IMetaDataImport::EnumInterfaceImpls (Método)
Enumera todas las interfaces implementadas `TypeDef`por el archivo .
  
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
 [adentro, fuera] Un puntero al enumerador.  
  
 `td`  
 [en] El token de TypeDef cuyos tokens MethodDef que representan implementaciones de interfaz deben enumerarse.  
  
 `rImpls`  
 [fuera] Matriz utilizada para almacenar los tokens MethodDef.  
  
 `cMax`  
 [en] La longitud máxima `rImpls` de la matriz.  
  
 `pcImpls`  
 [fuera] El número real de `rImpls`tokens devueltos en .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls`regresó con éxito.|  
|`S_FALSE`|No hay tokens MethodDef que enumerar. En ese `pcImpls` caso, se establece en cero.|  

## <a name="remarks"></a>Observaciones

La enumeración devuelve `mdInterfaceImpl` una colección de tokens `TypeDef`para cada interfaz implementada por el archivo . Los tokens de interfaz se devuelven en `DefineTypeDef` `SetTypeDefProps`el orden en que se especificaron las interfaces (a través de o ). Las propiedades `mdInterfaceImpl` de los tokens devueltos se pueden consultar mediante [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
