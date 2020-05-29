---
title: <Directives>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 0c6ebb8954e80f3f6dc6733f0e9d76094477689b
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202381"
---
# <a name="directives-element-net-native"></a>\<Directives>Elemento (.NET Native)
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
|`xmlns`|El espacio de nombres XML. Su valor es siempre `http://schemas.microsoft.com/netfx/2013/01/metadata` .|  
  
## <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.|  
|[\<Library>](library-element-net-native.md)|Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.  
  
 El `<Directives>` elemento puede contener cero o un [\<Application>](application-element-net-native.md) elemento, y cero, uno o más [\<Library>](library-element-net-native.md) elementos.  
  
## <a name="see-also"></a>Consulta también

- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementos de directivas en tiempo de ejecución](runtime-directive-elements.md)
