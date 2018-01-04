---
title: ICeeGen (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen
helpviewer_keywords: ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73af58ac55fd22e5b4f19f715cb0b1a137a640a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iceegen-interface"></a>ICeeGen (Interfaz)
Proporciona métodos para la compilación de código dinámico.  
  
 Esta interfaz está obsoleta y no debe usarse.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AddSectionReloc (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|Obsoleto. Agrega una instrucción .reloc al código base.|  
|[AllocateMethodBuffer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|Obsoleto. Crea un búfer del tamaño especificado para un método y obtiene la dirección virtual relativa del método.|  
|[ComputePointer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|Obsoleto. Determina el búfer para la sección de código especificada.|  
|[EmitString (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|Obsoleto. Emite la cadena especificada en el código base.|  
|[GenerateCeeFile (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|Obsoleto. Genera un archivo de base de código que contiene el código base actualmente cargado en esta `ICeeGen`.|  
|[GenerateCeeMemoryImage (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|Obsoleto. Genera una imagen en memoria para la base de código.|  
|[GetIlSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|Obsoleto. Obtiene la sección de la base de código de lenguaje intermedio al que hace referencia el identificador especificado.|  
|[GetIMapTokenIface (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|Obsoleto. Obtiene la interfaz al que hace referencia el token especificado.|  
|[GetMethodBuffer (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|Obsoleto. Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.|  
|[GetSectionBlock (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|Obsoleto. Obtiene un bloque de sección del código base.|  
|[GetSectionCreate (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|Obsoleto. Genera y obtiene una sección de código usando el nombre especificado y los valores de marca.|  
|[GetSectionDataLen (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|Obsoleto. Obtiene la longitud de la sección especificada.|  
|[GetString (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|Obsoleto. Obtiene la cadena almacenada en la dirección virtual relativa especificada.|  
|[GetStringSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|Obsoleto. Obtiene una representación de cadena de la sección de código al que hace referencia el identificador especificado.|  
|[TruncateSection (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|Obsoleto. Trunca la sección de código especificado por la longitud especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
