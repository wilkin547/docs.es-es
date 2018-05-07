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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04b6c04868efff31253b2d723c5783060382212b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps (Método)
Obtiene los metadatos asociados al campo al que hace referencia el token de FieldDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
#### <a name="parameters"></a>Parámetros  
 `mb`  
 [in] Símbolo (token) de FieldDef que representa el campo para obtener los metadatos asociados.  
  
 `pClass`  
 [out] Un puntero a un token de TypeDef que representa el tipo de la clase a la que pertenece el campo.  
  
 `szField`  
 [out] El nombre del campo.  
  
 `cchField`  
 [in] El tamaño en caracteres anchos del búfer de *szField*.  
  
 `pchField`  
 [out] El tamaño real del búfer devuelto.  
  
 `pdwAttr`  
 [out] Marcas asociadas a los metadatos del campo.  
  
 `ppvSigBlob`  
 [in] Un puntero al valor de metadatos binaria que describe el campo.  
  
 `pcbSigBlob`  
 [out] El tamaño en bytes de `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Una marca que especifica el tipo de valor del campo.  
  
 `ppValue`  
 [out] Un valor constante para el campo.  
  
 `pcchValue`  
 [out] El tamaño en caracteres de `ppValue`, o cero si no existe ninguna cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
