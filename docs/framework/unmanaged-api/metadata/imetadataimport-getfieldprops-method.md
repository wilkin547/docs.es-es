---
title: IMetaDataImport::GetFieldProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
ms.openlocfilehash: 462512fd2c2b33905b45bb67599b23b301fc71f7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437998"
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps (Método)
Obtiene los metadatos asociados al campo al que hace referencia el token de FieldDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mb`  
 de Un token de FieldDef que representa el campo para el que se van a obtener los metadatos asociados.  
  
 `pClass`  
 enuncia Un puntero a un token de TypeDef que representa el tipo de la clase a la que pertenece el campo.  
  
 `szField`  
 enuncia Nombre del campo.  
  
 `cchField`  
 de Tamaño en caracteres anchos del búfer para *szField*.  
  
 `pchField`  
 enuncia Tamaño real del búfer devuelto.  
  
 `pdwAttr`  
 enuncia Marcas asociadas a los metadatos del campo.  
  
 `ppvSigBlob`  
 de Puntero al valor de metadatos binarios que describe el campo.  
  
 `pcbSigBlob`  
 enuncia Tamaño en bytes de `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 enuncia Marca que especifica el tipo de valor del campo.  
  
 `ppValue`  
 enuncia Valor constante para el campo.  
  
 `pcchValue`  
 enuncia Tamaño en caracteres de `ppValue`, o cero si no existe ninguna cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
