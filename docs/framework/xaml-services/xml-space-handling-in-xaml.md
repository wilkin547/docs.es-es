---
title: "xml:space Handling in XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "XAML [XAML Services], xml:space attribute"
  - "XAML [XAML Services], whitespace processing"
  - "xml:space attribute [XAML Services]"
  - "whitespace processing [XAML Services]"
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 15
---
# xml:space Handling in XAML
El atributo `xml:space` es un atributo XML definido que declara el comportamiento de procesamiento significativo de espacio en blanco dentro de un elemento de objeto.  Este comportamiento es pertinente para todo el contenido \(texto interno\) incluido dentro del elemento donde se declara `xml:space` y también ámbitos a los elementos secundarios.  
  
## Uso de atributos XAML  
  
```  
<object xml:space="preserve" />  
```  
  
 \-O bien\-  
  
```  
<object xml:space="default" />  
```  
  
## Comentarios  
 La definición para el atributo `xml:space` en XAML que incluye sus dos valores posibles se deriva de `xml:space` definido como un "atributo especial" por especificaciones W3C para XML.  
  
 El valor predeterminado del atributo `xml:space` es el valor literal `"default"`.  Cuando su valor es `"default"`, o si no se indica `xml:space` en absoluto, el comportamiento de análisis del espacio en blanco significativo es la administración predeterminada, como se define en el tema [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
 Para conservar el espacio en blanco dentro del contenido de un elemento de objeto, especifique `xml:space="preserve"` para ese elemento de objeto.  
  
 Según la mayoría de interpretaciones, el ámbito de los efectos de atributo `xml:space` y su valor se aplica a los elementos secundarios.  
  
 Para obtener una discusión completa de procesamiento del espacio en blanco en XAML, vea [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## Vea también  
 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)   
 [Información general sobre XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)