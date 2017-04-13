---
title: "x:FieldModifier Directive | Microsoft Docs"
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
  - "FieldModifier attribute in XAML [XAML Services]"
  - "x:FieldModifier attribute [XAML Services]"
  - "XAML [XAML Services], x:FieldModifier attribute"
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 14
---
# x:FieldModifier Directive
Modifica el comportamiento de compilación de XAML, de tal forma que los campos correspondientes a las referencias de objetos con nombre se definen con el acceso <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, en lugar de definirse con el comportamiento <xref:System.Reflection.TypeAttributes?displayProperty=fullName> predeterminado.  
  
## Uso de atributos XAML  
  
```  
<object x:FieldModifier="Public".../>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|*Public*|La cadena exacta que se debe pasar para especificar el valor <xref:System.Reflection.TypeAttributes?displayProperty=fullName> en lugar de <xref:System.Reflection.TypeAttributes?displayProperty=fullName> varía en función del lenguaje de programación subyacente que se utilice.  Vea la sección Comentarios.|  
  
## Dependencias  
 Si una producción XAML usa `x:FieldModifier` en cualquier parte, el elemento raíz de esa producción XAML debe declarar [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md).  
  
## Comentarios  
 `x:FieldModifier` no es pertinente para declarar el nivel de acceso general de una clase o de sus miembros.  Sólo es pertinente para el comportamiento del procesamiento XAML cuando se procesa un objeto XAML determinado que forma parte de una producción XAML, y se vuelve un objeto que es accesible en el gráfico de objetos de una aplicación.  De manera predeterminada, la referencia de campo para este tipo de objeto se mantiene privada, lo que evita que los consumidores del control modifiquen el gráfico de objetos directamente.  En su lugar, se espera que los consumidores del control modifiquen el gráfico de objetos mediante modelos estándar habilitados por modelos de programación como, por ejemplo, obtener la raíz del diseño, colecciones de elementos secundarios, propiedades públicas dedicadas, etc.  
  
 El valor para el atributo `x:FieldModifier` varía en función del lenguaje de programación y su finalidad puede variar en marcos concretos.  La cadena que hay que utilizar depende de cómo implementa cada lenguaje su <xref:System.CodeDom.Compiler.CodeDomProvider> y de los convertidores de tipos que devuelve para definir los significados de <xref:System.Reflection.TypeAttributes?displayProperty=fullName> y <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, y de si el lenguaje distingue entre mayúsculas y minúsculas.  
  
-   Para [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], la cadena que se debe pasar para designar <xref:System.Reflection.TypeAttributes?displayProperty=fullName> es `public`.  
  
-   Para [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], la cadena que se debe pasar para designar <xref:System.Reflection.TypeAttributes?displayProperty=fullName> es `Public`.  
  
-   Para [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no existe actualmente ningún destino para XAML; por consiguiente, la cadena que se pasa es indefinida.  
  
 También se puede especificar <xref:System.Reflection.TypeAttributes?displayProperty=fullName> \(`internal` en [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Friend` en [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]\), pero especificar <xref:System.Reflection.TypeAttributes?displayProperty=fullName> es poco habitual porque `NotPublic` es ya el comportamiento predeterminado.  
  
 <xref:System.Reflection.TypeAttributes?displayProperty=fullName> es el comportamiento predeterminado porque es infrecuente que el código externo al ensamblado que compiló XAML necesite tener acceso a un elemento creado mediante XAML.  La arquitectura de seguridad de WPF y el comportamiento de compilación de XAML de forma combinada no declararán públicos los campos que almacenan instancias de elementos, a menos que se establezca `x:FieldModifier` específicamente para permitir el acceso público.  
  
 `x:FieldModifier` sólo es pertinente para los elementos que también tienen [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md), porque ese nombre se utiliza para hacer referencia al campo una vez que es público.  
  
 De forma predeterminada, la clase parcial del elemento raíz es pública; sin embargo, puede convertirla en no pública utilizando el objeto [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md) también afecta al nivel de acceso de la instancia de la clase del elemento raíz.  Puede incluir `x:Name` y `x:FieldModifier` en el elemento raíz, pero lo único que se consigue es una copia de campo público del elemento raíz, pero el nivel de acceso real de la clase del elemento raíz sigue estando controlado por [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
## Vea también  
 [Clases XAML y personalizadas para WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Código subyacente y XAML en WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md)   
 [Compilar una aplicación de WPF \(WPF\)](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)