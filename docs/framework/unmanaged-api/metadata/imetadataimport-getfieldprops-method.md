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
ms.openlocfilehash: 8c3f98a124dbbcae3b0500932a2357ed1757951f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177245"
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
 [en] Un token FieldDef que representa el campo para el que se van a obtener los metadatos asociados.  
  
 `pClass`  
 [fuera] Puntero a un token TypeDef que representa el tipo de la clase a la que pertenece el campo.  
  
 `szField`  
 [fuera] El nombre del campo.  
  
 `cchField`  
 [en] El tamaño en caracteres anchos del búfer para *szField*.  
  
 `pchField`  
 [fuera] El tamaño real del búfer devuelto.  
  
 `pdwAttr`  
 [fuera] Indicadores asociados a los metadatos del campo.  
  
 `ppvSigBlob`  
 [en] Puntero al valor de metadatos binarios que describe el campo.  
  
 `pcbSigBlob`  
 [fuera] El tamaño en `ppvSigBlob`bytes de .  
  
 `pdwCPlusTypeFlag`  
 [fuera] Marca que especifica el tipo de valor del campo.  
  
 `ppValue`  
 [fuera] Un valor constante para el campo.  
  
 `pcchValue`  
 [fuera] El tamaño en `ppValue`caracteres de , o cero si no existe ninguna cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
