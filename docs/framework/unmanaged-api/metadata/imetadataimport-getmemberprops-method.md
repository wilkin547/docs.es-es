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
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177229"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps (Método)
Obtiene información almacenada en los metadatos de una definición de miembro especificada, incluido <xref:System.Type> el nombre, la firma binaria y la dirección virtual relativa, del miembro al que hace referencia el token de metadatos especificado. Este es un método auxiliar simple: si *mb* es un MethodDef, a continuación, **GetMethodProps** se llama; si *mb* es un FieldDef, a continuación, **GetFieldProps** se llama. Consulte estos otros métodos para obtener más información.
  
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
 [en] El token que hace referencia al miembro para el que se obtienen los metadatos asociados.  
  
 `pClass`  
 [fuera] Puntero al token de metadatos que representa la clase del miembro.  
  
 `szMember`  
 [fuera] El nombre del miembro.  
  
 `cchMember`  
 [en] El tamaño en caracteres anchos del `szMember` búfer.  
  
 `pchMember`  
 [fuera] El tamaño en caracteres anchos del nombre devuelto.  
  
 `pdwAttr`  
 [fuera] Cualquier valor de marca aplicado al miembro.  
  
 `ppvSigBlob`  
 [fuera] Un puntero a la firma de metadatos binarios del miembro.  
  
 `pcbSigBlob`  
 [fuera] El tamaño en `ppvSigBlob`bytes de .  
  
 `pulCodeRVA`  
 [fuera] Un puntero a la dirección virtual relativa del miembro.  
  
 `pdwImplFlags`  
 [fuera] Cualquier indicador de implementación de método asociado con el miembro.  
  
 `pdwCPlusTypeFlag`  
 [fuera] Una bandera que <xref:System.ValueType>marca un archivo . Es uno de `ELEMENT_TYPE_*` los valores.
  
 `ppValue`  
 [fuera] Un valor de cadena constante devuelto por este miembro.  
  
 `pcchValue`  
 [fuera] El tamaño en `ppValue`caracteres `ppValue` de , o cero si no contiene una cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
