---
title: "PresentationOptions:Freeze (Atributo) | Microsoft Docs"
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
  - "Freezable (elementos)"
  - "Freeze (atributo)"
  - "PresentationOptions (prefijo)"
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# PresentationOptions:Freeze (Atributo)
Establece el estado de <xref:System.Windows.Freezable.IsFrozen%2A> en `true` para el elemento <xref:System.Windows.Freezable> contenedor.  El comportamiento predeterminado de un elemento <xref:System.Windows.Freezable> cuyo atributo `PresentationOptions:Freeze` no se especifica que el valor de <xref:System.Windows.Freezable.IsFrozen%2A> es `false` en tiempo de carga y depende del comportamiento de <xref:System.Windows.Freezable> general en tiempo de ejecución.  
  
## Uso de atributos XAML  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`PresentationOptions`|Un prefijo de espacio de nombres XML, que puede ser cualquier cadena del prefijo válida, conforme con la especificación XML 1.0.  El prefijo `PresentationOptions` se utiliza con fines de identificación en esta documentación.|  
|`freezableElement`|Un elemento que crea una instancia de cualquier clase derivada de <xref:System.Windows.Freezable>.|  
  
## Comentarios  
 El atributo `Freeze` es el único atributo u otro elemento de programación definido en el espacio de nombres XML `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.  El atributo `Freeze` existe específicamente en este espacio de nombres especial para que se pueda designar como omitible, utilizando [Atributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) como parte de las declaraciones del elemento raíz.  El motivo por el que `Freeze` debe ser omitible es que no todas las implementaciones de procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pueden inmovilizar un elemento <xref:System.Windows.Freezable> en tiempo de carga; esta función no forma parte de la especificación [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 La capacidad de procesar el atributo `Freeze` se integra de manera específica en el procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que procesa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para las aplicaciones compiladas.  No todas las clases admiten el atributo, cuya sintaxis no es extensible ni modificable.  Si está implementando su propio procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede optar por imitar el comportamiento de inmovilización del procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al procesar el atributo `Freeze` de los elementos <xref:System.Windows.Freezable> en tiempo de carga.  
  
 Cualquier valor del atributo `Freeze` que no sea `true` \(sin distinción de mayúsculas y minúsculas\) genera un error en tiempo de carga.  \(Especificar el atributo `Freeze` como `false` no es un error, pero éste ya es el valor predeterminado, de manera que establecerlo en `false` no surte ningún efecto.\)  
  
## Vea también  
 <xref:System.Windows.Freezable>   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Atributo mc:Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)