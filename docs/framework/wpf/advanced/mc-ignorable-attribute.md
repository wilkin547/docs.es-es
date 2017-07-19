---
title: "Atributo mc:Ignorable | Microsoft Docs"
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
  - "mc (prefijo de espacio de nombres XML)"
  - "mc:Ignorable (atributo)"
  - "mc:ProcessContent (atributo)"
  - "XAML, mc:Ignorable (atributo)"
  - "XAML, mc:ProcessContent (atributo)"
  - "XML, mc (prefijo de espacio de nombres)"
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Atributo mc:Ignorable
Especifica qué prefijos de espacios de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] de un archivo de marcado puede omitir un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  El atributo `mc:Ignorable` admite la compatibilidad de marcado para la asignación de espacios de nombres personalizados y para el control de versiones [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
## Uso de atributos XAML \(un solo prefijo\)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## Uso de atributos XAML \(dos prefijos\)  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1, etc.*|Cualquier cadena de prefijo válida, de acuerdo con la especificación de XML 1.0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, de acuerdo con la especificación de XML 1.0.|  
|*ThisElementCanBeIgnored*|Elemento que las implementaciones del procesador [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pueden omitir si no se puede resolver el tipo subyacente.|  
  
## Comentarios  
 El prefijo de espacio de nombres `mc` de [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] es la convención de prefijo recomendada para su uso al asignar el espacio de nombres de compatibilidad con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Los elementos o atributos cuya parte del prefijo del nombre de elemento se identifique como `mc:Ignorable` no generarán errores al procesarlos en un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Si ese atributo no se pudo resolver como un tipo subyacente o una construcción de programación, el elemento se omite.  Sin embargo, tenga en cuenta que los elementos omitidos pueden generar errores de análisis adicionales correspondientes a otros requisitos del elemento; estos errores son los efectos secundarios por el hecho de no procesar el elemento.  Por ejemplo, puede que el modelo de contenido de un elemento determinado requiera exactamente un elemento secundario, pero si el elemento secundario especificado se encuentra en un prefijo `mc:Ignorable`, y además no se puede resolver como un tipo, el procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede generar un error.  
  
 `mc:Ignorable` solamente se aplica a las asignaciones de espacio de nombres a cadenas de identificador.  `mc:Ignorable` no se aplica a las asignaciones de espacio de nombres a ensamblados, en las que se especifica un espacio de nombres [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] y un ensamblado \(o cuyo valor predeterminado de ensamblado es la aplicación ejecutable actual\).  
  
 Si está implementando un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], dicha implementación no debe generar errores de análisis ni de procesamiento al resolver los tipos de ningún elemento o atributo calificado por un prefijo identificado como `mc:Ignorable`.  No obstante, la implementación del procesador sí puede producir excepciones que sean el efecto secundario del hecho de no cargar o procesar un elemento, como en el ejemplo anterior de un solo elemento secundario.  
  
 De manera predeterminada, un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] omitirá el contenido incluido en un elemento omitido.  Sin embargo, puede especificar un atributo adicional, [mc:ProcessContent \(Atributo\)](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), para exigir el procesamiento continuado del contenido incluido en un elemento omitido por parte del siguiente elemento primario disponible.  
  
 Se pueden especificar varios prefijos en el atributo, utilizando uno o más caracteres de espacio en blanco como separadores, por ejemplo: `mc:Ignorable="ignore1 ignore2"`.  
  
 El espacio de nombres [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] define otros elementos y atributos que se documentan en esta sección del [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].  Para obtener más información, vea [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## Vea también  
 <xref:System.Windows.Markup.XamlReader>   
 [PresentationOptions:Freeze \(Atributo\)](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)