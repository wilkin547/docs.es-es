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
ms.openlocfilehash: 2bd05b49c3d51ac13865997910c99cc0cd5ca2d9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491269"
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
 enuncia Tamaño en bytes de `ppvSigBlob` .  
  
 `pdwCPlusTypeFlag`  
 enuncia Marca que especifica el tipo de valor del campo.  
  
 `ppValue`  
 enuncia Valor constante para el campo.  
  
 `pcchValue`  
 enuncia Tamaño en caracteres de `ppValue` , o cero si no existe ninguna cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
