---
title: "&lt;add&gt; de &lt;namespaceTable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; de &lt;namespaceTable&gt;
Representa un elemento de configuración que contiene un espacio de nombres para prefijar la asignación que después puede usarse en filtros XPath para el enrutamiento.  
  
## Sintaxis  
  
```vb  
  
<routing>  
   <namespaceTable>  
     <add namespace="String" prefix="String" />   
   </namespaceTable>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|namespace|Cadena que contiene el espacio de nombres.|  
|prefix|Cadena que contiene el prefijo para este espacio de nombres.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<namespaceTable\>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|Representa una sección de configuración para definir un conjunto de elementos que contienen el espacio de nombres para prefijar asignaciones que se pueden utilizar a continuación en filtros XPath para el enrutamiento.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.NamespaceElement](assetId:///System.ServiceModel.Routing.Configuration.NamespaceElement?qualifyHint=False&amp;autoUpgrade=True)