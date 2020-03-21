---
title: IMetaDataImport::GetPropertyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175335"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps (Método)
Obtiene los metadatos de la propiedad representada por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,
   [out] LPCWSTR           szProperty,
   [in]  ULONG             cchProperty,
   [out] ULONG             *pchProperty,
   [out] DWORD             *pdwPropFlags,
   [out] PCCOR_SIGNATURE   *ppvSig,
   [out] ULONG             *pbSig,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,
   [out] mdMethodDef       *pmdGetter,
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,
   [out] ULONG             *pcOtherMethod
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `prop`  
 [en] Un token que representa la propiedad para la que se va a devolver metadatos.  
  
 `pClass`  
 [fuera] Puntero al token TypeDef que representa el tipo que implementa la propiedad.  
  
 `szProperty`  
 [fuera] Un búfer para contener el nombre de propiedad.  
  
 `cchProperty`  
 [en] El tamaño en `szProperty`caracteres anchos de .  
  
 `pchProperty`  
 [fuera] El número de caracteres anchos devueltos en `szProperty`.  
  
 `pdwPropFlags`  
 [fuera] Puntero a cualquier marca de atributo aplicada a la propiedad. Este valor es una máscara de bits de la [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeración.  
  
 `ppvSig`  
 [fuera] Un puntero a la firma de metadatos de la propiedad.  
  
 `pbSig`  
 [fuera] El número de `ppvSig`bytes devueltos en .  
  
 `pdwCPlusTypeFlag`  
 [fuera] Marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad. Este valor procede de la enumeración CorElementType.  
  
 `ppDefaultValue`  
 [fuera] Puntero a los bytes que almacenan el valor predeterminado de esta propiedad.  
  
 `pcchDefaultValue`  
 [fuera] El tamaño en `ppDefaultValue`caracteres `pdwCPlusTypeFlag` anchos de , if es ELEMENT_TYPE_STRING; de lo contrario, este valor no es relevante. En ese caso, `ppDefaultValue` la longitud de se deduce del `pdwCPlusTypeFlag`tipo especificado por .  
  
 `pmdSetter`  
 [fuera] Puntero al token MethodDef que representa el método de descriptor de acceso set para la propiedad.  
  
 `pmdGetter`  
 [fuera] Puntero al token MethodDef que representa el método de descriptor de acceso get para la propiedad.  
  
 `rmdOtherMethod`  
 [fuera] Matriz de tokens MethodDef que representan otros métodos asociados a la propiedad.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`. Si no proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin previo aviso.  
  
 `pcOtherMethod`  
 [fuera] El número de tokens MethodDef devueltos en `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
