---
title: '&lt;add&gt; de &lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f08f4b46c6e6290602fc78a2f06954b9cf0b07d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a>&lt;add&gt; de &lt;namespaceTable&gt;
Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.  
  
 \<system.serviceModel >  
\<enrutamiento >  
\<namespaceTable >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|namespace|Cadena que contiene el espacio de nombres.|  
|prefix|Cadena que contiene el prefijo para este espacio de nombres.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<namespaceTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
