---
title: IMetaDataImport2::GetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
ms.openlocfilehash: d335beecc12e0c1c895e42888ad7172f78062ff7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702546"
---
# <a name="imetadataimport2getpekind-method"></a>IMetaDataImport2::GetPEKind (Método)

Obtiene un valor que identifica la naturaleza del código en el archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, que se define en el ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pdwPEKind`  
 enuncia Un puntero a un valor de la enumeración [CorPEKind (](corpekind-enumeration.md) que describe el archivo PE.  
  
 `pdwMachine`  
 enuncia Un puntero a un valor que identifica la arquitectura de la máquina. Vea la sección siguiente para ver los posibles valores.  
  
## <a name="remarks"></a>Comentarios  

 El valor al que hace referencia el `pdwMachine` parámetro puede ser uno de los siguientes.  
  
|Value|Arquitectura de la máquina|  
|-----------|--------------------------|  
|IMAGE_FILE_MACHINE_I386<br /><br /> 0x014C|x86|  
|IMAGE_FILE_MACHINE_IA64<br /><br /> 0x0200|IPF de Intel|  
|IMAGE_FILE_MACHINE_AMD64<br /><br /> 0x8664|x64|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [CorPEKind (Enumeración)](corpekind-enumeration.md)
