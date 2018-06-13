---
title: Elemento &lt;Directives&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd571255f924c9f3878c00a2bc01397d63e6d777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394451"
---
# <a name="ltdirectivesgt-element-net-native"></a>Elemento &lt;Directives&gt; (.NET Native)
Elemento raíz de cada archivo de directivas de tiempo de ejecución para [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **\<Directivas xmlns = "http://schemas.microsoft.com/netfx/2013/01/metadata" >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`xmlns`|El espacio de nombres XML. Su valor es siempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.|  
  
## <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.  
  
 El elemento `<Directives>` puede contener cero o un elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) y cero, uno o más elementos [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
## <a name="see-also"></a>Vea también  
 [Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)](../../../docs/framework/net-native/runtime-directive-elements.md)
