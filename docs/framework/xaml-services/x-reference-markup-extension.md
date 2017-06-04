---
title: "x:Reference Markup Extension | Microsoft Docs"
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
  - "x:Reference markup extension [XAML Services]"
  - "XAML [XAML Services], x:Reference Markup Extension"
  - "Reference markup extension [XAML Services]"
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# x:Reference Markup Extension
Hace referencia a una instancia que se declara en otra parte del marcado XAML.  La referencia hace referencia a `x:Name` de un elemento.  
  
## Uso de atributos XAML  
  
```  
<object property="{x:Reference instancexName}" .../>  
```  
  
## Uso de elementos de objeto XAML  
  
```  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`instancexName`|El valor `x:Name` \(o valor de propiedad identificado por <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>\) de la instancia a la que se hace referencia.|  
  
## Comentarios  
 `x:Reference` proporciona soporte con el nivel de lenguaje XAML para un concepto de referencia de elemento que se implementaba de otro modo en marcos concretos como WPF.  
  
## x:Reference y WPF  
 En WPF y XAML 2006, las referencias de elementos se direccionan mediante la característica de enlace <xref:System.Windows.Data.Binding.ElementName%2A> de nivel de marco.  Para la mayoría de las aplicaciones y escenarios de WPF, todavía se debería utilizar el enlace <xref:System.Windows.Data.Binding.ElementName%2A>.  Las excepciones a esta orientación general podrían incluir los casos en los que hay contexto de datos u otras consideraciones de ámbito que hacen el enlace de datos poco práctico, y en los que la compilación de marcado no está implicada.  
  
 `x:Reference` es una construcción definida en XAML 2009.  En WPF, puede utilizar características de XAML 2009, pero solo para XAML que no se compila mediante marcado WPF.  El formato BAML de XAML y XAML compilado por marcado actualmente no admiten las palabras claves y características del lenguaje de XAML 2009.