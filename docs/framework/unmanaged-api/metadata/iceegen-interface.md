---
title: ICeeGen (Interfaz)
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: ae3c372951de00b097d0a8437039a3a85bf3aabf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426151"
---
# <a name="iceegen-interface"></a>ICeeGen (Interfaz)
Proporciona métodos para la compilación de código dinámico.  
  
 Esta interfaz está obsoleta y no debe usarse.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AddSectionReloc (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Obsoleto. Agrega una instrucción. reloc al código base.|  
|[AllocateMethodBuffer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Obsoleto. Crea un búfer con el tamaño especificado para un método y obtiene la dirección virtual relativa del método.|  
|[ComputePointer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Obsoleto. Determina el búfer para la sección de código especificada.|  
|[EmitString (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Obsoleto. Emite la cadena especificada en el código base.|  
|[GenerateCeeFile (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Obsoleto. Genera un archivo de código base que contiene la base de código cargada actualmente en este `ICeeGen`.|  
|[GenerateCeeMemoryImage (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Obsoleto. Genera una imagen en memoria para la base de código.|  
|[GetIlSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Obsoleto. Obtiene la sección de la base de código de lenguaje intermedio a la que hace referencia el identificador especificado.|  
|[GetIMapTokenIface (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Obsoleto. Obtiene la interfaz a la que hace referencia el token especificado.|  
|[GetMethodBuffer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Obsoleto. Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.|  
|[GetSectionBlock (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Obsoleto. Obtiene un bloque de sección del código base.|  
|[GetSectionCreate (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Obsoleto. Genera y obtiene una sección de código usando el nombre y los valores de marca especificados.|  
|[GetSectionDataLen (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Obsoleto. Obtiene la longitud de la sección especificada.|  
|[GetString (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Obsoleto. Obtiene la cadena almacenada en la dirección virtual relativa especificada.|  
|[GetStringSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Obsoleto. Obtiene una representación de cadena de la sección de código a la que hace referencia el identificador especificado.|  
|[TruncateSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Obsoleto. Trunca la sección de código especificada según la longitud especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
