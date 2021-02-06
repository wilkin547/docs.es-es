---
description: 'Más información sobre: <Directives> elemento (.net Native)'
title: <Directives> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 7aa3bf3718f32d55ba8189c65705868c6fb399ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662915"
---
# <a name="directives-element-net-native"></a>\<Directives> Elemento (.NET Native)

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
  
## <a name="remarks"></a>Observaciones  

 Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.  
  
 El `<Directives>` elemento puede contener cero o un [\<Application>](application-element-net-native.md) elemento, y cero, uno o más [\<Library>](library-element-net-native.md) elementos.  
  
## <a name="see-also"></a>Vea también

- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementos de directivas en tiempo de ejecución](runtime-directive-elements.md)
