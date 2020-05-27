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
ms.openlocfilehash: e6cf0aa6f731d0a417e1a2be0ca1d0f8c9299379
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008279"
---
# <a name="iceegen-interface"></a>ICeeGen (Interfaz)
Proporciona métodos para la compilación de código dinámico.  
  
 Esta interfaz está obsoleta y no debe usarse.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AddSectionReloc](iceegen-addsectionreloc-method.md)|Obsoleto. Agrega una instrucción. reloc al código base.|  
|[Método AllocateMethodBuffer](iceegen-allocatemethodbuffer-method.md)|Obsoleto. Crea un búfer con el tamaño especificado para un método y obtiene la dirección virtual relativa del método.|  
|[Método ComputePointer](iceegen-computepointer-method.md)|Obsoleto. Determina el búfer para la sección de código especificada.|  
|[Método EmitString](iceegen-emitstring-method.md)|Obsoleto. Emite la cadena especificada en el código base.|  
|[Método GenerateCeeFile](iceegen-generateceefile-method.md)|Obsoleto. Genera un archivo de código base que contiene el código base cargado actualmente en este `ICeeGen` .|  
|[Método GenerateCeeMemoryImage](iceegen-generateceememoryimage-method.md)|Obsoleto. Genera una imagen en memoria para la base de código.|  
|[Método GetIlSection](iceegen-getilsection-method.md)|Obsoleto. Obtiene la sección de la base de código de lenguaje intermedio a la que hace referencia el identificador especificado.|  
|[Método GetIMapTokenIface](iceegen-getimaptokeniface-method.md)|Obsoleto. Obtiene la interfaz a la que hace referencia el token especificado.|  
|[Método GetMethodBuffer](iceegen-getmethodbuffer-method.md)|Obsoleto. Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.|  
|[Método GetSectionBlock](iceegen-getsectionblock-method.md)|Obsoleto. Obtiene un bloque de sección del código base.|  
|[Método GetSectionCreate](iceegen-getsectioncreate-method.md)|Obsoleto. Genera y obtiene una sección de código usando el nombre y los valores de marca especificados.|  
|[Método GetSectionDataLen](iceegen-getsectiondatalen-method.md)|Obsoleto. Obtiene la longitud de la sección especificada.|  
|[GetString (Método)](iceegen-getstring-method.md)|Obsoleto. Obtiene la cadena almacenada en la dirección virtual relativa especificada.|  
|[Método GetStringSection](iceegen-getstringsection-method.md)|Obsoleto. Obtiene una representación de cadena de la sección de código a la que hace referencia el identificador especificado.|  
|[Método TruncateSection](iceegen-truncatesection-method.md)|Obsoleto. Trunca la sección de código especificada según la longitud especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de metadatos](metadata-interfaces.md)
