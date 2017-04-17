---
title: "x:ClassModifier Directive | Microsoft Docs"
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
  - "xClassModifier"
  - "x:ClassModifier"
  - "ClassModifier"
helpviewer_keywords: 
  - "XAML [XAML Services], x:ClassModifier attribute"
  - "x:ClassModifier attribute [XAML Services]"
  - "ClassModifier attribute in XAML [XAML Services]"
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: 22
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 21
---
# x:ClassModifier Directive
Modifica el comportamiento de compilación de XAML si se proporciona también `x:Class`.  En concreto, en lugar de crear una `class` parcial con nivel de acceso `Public` \(valor predeterminado\), el objeto `x:Class` proporcionado se crea con un nivel de acceso `NotPublic`.  Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.  
  
## Uso de atributos XAML  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|*NotPublic*|La cadena exacta que se debe pasar para especificar el valor <xref:System.Reflection.TypeAttributes?displayProperty=fullName> en lugar de <xref:System.Reflection.TypeAttributes?displayProperty=fullName> varía en función del lenguaje de programación subyacente que se utilice.  Vea la sección Comentarios.|  
  
## Dependencias  
 [x:Class](../../../docs/framework/xaml-services/x-class-directive.md) también se debe proporcionar para el mismo elemento, que debe ser el elemento raíz de una página.  Para obtener más información, vea [\[MS\-XAML\] sección 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Comentarios  
 El valor de `x:ClassModifier` al usarlo en los servicios XAML de .NET Framework varía en función del lenguaje de programación.  La cadena que hay que utilizar depende de cómo implementa cada lenguaje su <xref:System.CodeDom.Compiler.CodeDomProvider> y de los convertidores de tipos que devuelve para definir los significados de <xref:System.Reflection.TypeAttributes?displayProperty=fullName> y <xref:System.Reflection.TypeAttributes?displayProperty=fullName>, y de si el lenguaje distingue entre mayúsculas y minúsculas.  
  
-   Para [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], la cadena que se debe pasar para designar <xref:System.Reflection.TypeAttributes?displayProperty=fullName> es `internal`.  
  
-   Para [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], la cadena que se debe pasar para designar <xref:System.Reflection.TypeAttributes?displayProperty=fullName> es `Friend`.  
  
-   Para [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no existen destinos compatibles con la compilación XAML, por consiguiente, el valor para pasar no está especificado.  
  
 También puede especificar <xref:System.Reflection.TypeAttributes?displayProperty=fullName> \(`public` en [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` en [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]\); sin embargo, <xref:System.Reflection.TypeAttributes?displayProperty=fullName> no se especifica con frecuencia, porque <xref:System.Reflection.TypeAttributes?displayProperty=fullName> ya es el comportamiento predeterminado.  
  
 Otros valores con restricciones de nivel de acceso de código de usuario equivalentes, tales como `private` en [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], no son pertinentes para `x:ClassModifier`, porque las referencias de clase anidadas no se admiten en XAML y, en consecuencia, el modificador <xref:System.Reflection.TypeAttributes?displayProperty=fullName> tiene el mismo efecto.  
  
## Notas de seguridad  
 El nivel de acceso tal y como se declara en `x:ClassModifier` todavía está sujeto a la interpretación por marcos determinados y sus capacidades.  WPF incluye las funciones para cargar y crear instancias de los tipos donde `x:ClassModifier` es `internal`, si se hace referencia a esa clase desde un recurso WPF a través de una referencia al indicador pack URI.  Como consecuencia de este caso y posiblemente otros casos como él, no confíe exclusivamente en `x:ClassModifier` para bloquear todos los intentos posibles de creación de instancias.  
  
## Vea también  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Código subyacente y XAML en WPF](../../../ocs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:FieldModifier Directive](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)   
 [Seguridad \(WPF\)](../../../ocs/framework/wpf/security-wpf.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)