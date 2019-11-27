---
title: IMetaDataImport::GetMemberProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: bc5bbba2fa4a95955e52a2e083a2097178b5d96a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437520"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps (Método)
Obtiene información almacenada en los metadatos de una definición de miembro especificada, incluidos el nombre, la firma binaria y la dirección virtual relativa, del miembro de <xref:System.Type> al que hace referencia el token de metadatos especificado. Se trata de un método auxiliar sencillo: Si *MB* es un MethodDef, se llama a **GetMethodProps (** ; Si *MB* es un FieldDef, se llama a **getfieldprops (** . Consulte estos otros métodos para obtener más información. 
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] ULONG             *pulCodeRVA,   
   [out] DWORD             *pdwImplFlags,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `mb`  
 de Token que hace referencia al miembro para el que se van a obtener los metadatos asociados.  
  
 `pClass`  
 enuncia Puntero al símbolo (token) de metadatos que representa la clase del miembro.  
  
 `szMember`  
 enuncia Nombre del miembro.  
  
 `cchMember`  
 de Tamaño en caracteres anchos del búfer `szMember`.  
  
 `pchMember`  
 enuncia Tamaño en caracteres anchos del nombre devuelto.  
  
 `pdwAttr`  
 enuncia Los valores de marca aplicados al miembro.  
  
 `ppvSigBlob`  
 enuncia Puntero a la firma de metadatos binarios del miembro.  
  
 `pcbSigBlob`  
 enuncia Tamaño en bytes de `ppvSigBlob`.  
  
 `pulCodeRVA`  
 enuncia Puntero a la dirección virtual relativa del miembro.  
  
 `pdwImplFlags`  
 enuncia Cualquier marcador de implementación de método asociado al miembro.  
  
 `pdwCPlusTypeFlag`  
 enuncia Marca que marca un <xref:System.ValueType>. Es uno de los valores de `ELEMENT_TYPE_*`.
  
 `ppValue`  
 enuncia Un valor de cadena constante devuelto por este miembro.  
  
 `pcchValue`  
 enuncia Tamaño en caracteres de `ppValue`, o cero si `ppValue` no contiene una cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
