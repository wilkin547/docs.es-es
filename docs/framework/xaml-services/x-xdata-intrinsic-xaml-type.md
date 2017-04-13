---
title: "x:XData Intrinsic XAML Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:XData"
  - "XData"
  - "xXData"
helpviewer_keywords: 
  - "XAML [XAML Services], x:XData directive element"
  - "XData in XAML [XAML Services]"
  - "x:XData XAML directive element [XAML Services]"
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: 17
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 17
---
# x:XData Intrinsic XAML Type
Habilita la colocación de islas de datos XML dentro de una producción XAML.  Los procesadores XAML no deben tratar los elementos XML incluidos en `x:XData` como si fueran una parte del espacio de nombres XAML predeterminado activo o de cualquier otro espacio de nombres XAML.  `x:XData` puede contener XML arbitrario con formato correcto.  
  
## Uso de elementos de objeto XAML  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`elementDataRoot`|El único elemento raíz de la isla de datos adjunta.  Para la mayoría de los consumidores eventuales, XML que no tiene una raíz única que se considere no válida.  En concreto, se requiere una sola raíz si `x:XData` está pensado como origen de datos XML de WPF o de muchas otras tecnologías que usan los orígenes XML para el enlace de datos.|  
|`[elementData]`|Opcional.  XML que representa los datos XML.  Cualquier número de elementos se puede contener como datos de elementos, y los elementos anidados se pueden contener en otros elementos; sin embargo, se aplican las reglas generales de XML.|  
  
## Comentarios  
 Los elementos XML dentro de un objeto `x:XData` pueden volver a declarar todos los posibles espacios de nombres y prefijos del contenedor XMLDOM dentro de los datos.  
  
 El acceso mediante programación a los datos XML y al tipo XAML intrínseco `x:XData` es posible en los servicios XAML de .NET Framework a través de la clase <xref:System.Windows.Markup.XData>.  
  
## Notas de uso de WPF  
 El objeto `x:XData` se utiliza principalmente como objeto secundario de <xref:System.Windows.Data.XmlDataProvider> o bien, como alternativa, como el objeto secundario de la propiedad <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName> de la propiedad \( en XAML, esto se expresa normalmente en sintaxis de propiedades de elemento\).  
  
 Normalmente, los datos deberían volver a definir el espacio de nombres XML base dentro de la isla de datos de manera que sea un nuevo espacio de nombres XML predeterminado \(establecido en una cadena vacía\).  Es lo más fácil para las islas de datos simples, porque las expresiones <xref:System.Windows.Data.Binding.XPath%2A> utilizadas para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos.  En las islas de datos más complejas podrían definirse varios prefijos para los datos y utilizarse un prefijo concreto para el espacio de nombres XML de la raíz.  En este caso, todas las referencias a las expresiones <xref:System.Windows.Data.Binding.XPath%2A> deberán incluir el prefijo adecuado asignado por el espacio de nombres.  Para obtener más información, vea [Información general sobre el enlace de datos](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Técnicamente, `x:XData` se pueden utilizar como contenido de cualquier propiedad de tipo <xref:System.Xml.Serialization.IXmlSerializable>.  Sin embargo, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName>. es la única implementación notable.  
  
## Vea también  
 <xref:System.Windows.Data.XmlDataProvider>   
 [Información general sobre el enlace de datos](../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Enlazar extensión de marcado](../../../docs/framework/wpf/advanced/binding-markup-extension.md)