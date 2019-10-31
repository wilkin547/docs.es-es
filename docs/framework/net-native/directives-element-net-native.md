---
title: Elemento <Directives> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: abe2e7221e0afb984a6178b12fabc36ea24deb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128467"
---
# <a name="directives-element-net-native"></a>\<directivas > elemento (.NET Native)
Elemento raíz de cada archivo de directivas en tiempo de ejecución para .NET Native.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`xmlns`|El espacio de nombres XML. Su valor siempre es **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .|  
  
## <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.|  
|[\<Library>](library-element-net-native.md)|Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.  
  
 El elemento `<Directives>` puede contener cero o un elemento [\<Application>](application-element-net-native.md) y cero, uno o más elementos [\<Library>](library-element-net-native.md).  
  
## <a name="see-also"></a>Vea también

- [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) (Referencia del archivo de configuración de directivas en tiempo de ejecución [rd.xml])
- [Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)](runtime-directive-elements.md)
