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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fb081c48abf899b44da1c1351efa3f6036f1c8d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176129"
---
# <a name="iceegen-interface"></a>ICeeGen (Interfaz)
Proporciona métodos para la compilación de código dinámico.  
  
 Esta interfaz está obsoleta y no debe usarse.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AddSectionReloc (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Obsoleto. Agrega una instrucción .reloc al código base.|  
|[AllocateMethodBuffer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Obsoleto. Crea un búfer del tamaño especificado para un método y obtiene la dirección virtual relativa del método.|  
|[ComputePointer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Obsoleto. Determina el búfer para la sección de códigos especificada.|  
|[EmitString (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Obsoleto. Emite la cadena especificada en la base de código.|  
|[GenerateCeeFile (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Obsoleto. Genera un archivo de base de código que contiene el código base actualmente cargado en esta `ICeeGen`.|  
|[GenerateCeeMemoryImage (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Obsoleto. Genera una imagen en memoria para la base de código.|  
|[GetIlSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Obsoleto. Obtiene la sección de la base de código de lenguaje intermedio al que hace referencia el identificador especificado.|  
|[GetIMapTokenIface (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Obsoleto. Obtiene la interfaz al que hace referencia el token especificado.|  
|[GetMethodBuffer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Obsoleto. Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.|  
|[GetSectionBlock (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Obsoleto. Obtiene un bloque de sección del código base.|  
|[GetSectionCreate (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Obsoleto. Genera y obtiene una sección de código con el nombre especificado y los valores de marca.|  
|[GetSectionDataLen (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Obsoleto. Obtiene la longitud de la sección especificada.|  
|[GetString (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Obsoleto. Obtiene la cadena almacenada en la dirección virtual relativa especificada.|  
|[GetStringSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Obsoleto. Obtiene una representación de cadena de la sección de código al que hace referencia el identificador especificado.|  
|[TruncateSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Obsoleto. Trunca la sección de código especificado por la longitud especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Usar como un recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
