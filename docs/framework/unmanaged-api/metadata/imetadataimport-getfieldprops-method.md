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
ms.openlocfilehash: fc4e8140485902e4677bca0228bc125c64b497f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671868"
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
 [in] Un token de FieldDef que representa el campo para obtener los metadatos asociados.  
  
 `pClass`  
 [out] Un puntero a un token de TypeDef que representa el tipo de la clase a la que pertenece el campo.  
  
 `szField`  
 [out] El nombre del campo.  
  
 `cchField`  
 [in] El tamaño en caracteres anchos del búfer para *szField*.  
  
 `pchField`  
 [out] El tamaño real del búfer devuelto.  
  
 `pdwAttr`  
 [out] Marcas asociadas a los metadatos del campo.  
  
 `ppvSigBlob`  
 [in] Un puntero al valor binario de metadatos que describe el campo.  
  
 `pcbSigBlob`  
 [out] El tamaño en bytes de `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Una marca que especifica el tipo de valor del campo.  
  
 `ppValue`  
 [out] Un valor constante para el campo.  
  
 `pcchValue`  
 [out] El tamaño en caracteres de `ppValue`, o cero si no existe ninguna cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
