---
description: 'Más información sobre: IMetaDataImport:: Getmemberrefprops ((método)'
title: IMetaDataImport::GetMemberRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: b441f39d95c9af1e18d34a1a4d86d6cea33508c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783888"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>IMetaDataImport::GetMemberRefProps (Método)

Obtiene los metadatos asociados al miembro al que hace referencia el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `mr`  
 de Token de MemberRef para el que se van a devolver los metadatos asociados.  
  
 `ptk`  
 enuncia Un token TypeDef o TypeRef, o TypeSpec que representa la clase que declara el miembro, o un token ModuleRef que representa la clase de módulo que declara el miembro, o un MethodDef que representa el miembro.  
  
 `szMember`  
 enuncia Un búfer de cadena para el nombre del miembro.  
  
 `cchMember`  
 de Tamaño solicitado en caracteres anchos de `szMember` .  
  
 `pchMember`  
 enuncia Tamaño devuelto en caracteres anchos de `szMember` .  
  
 `ppvSibBlob`  
 enuncia Puntero a la firma de metadatos binarios para el miembro.  
  
 `pbSig`  
 enuncia Tamaño en bytes de `ppvSigBlob` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
