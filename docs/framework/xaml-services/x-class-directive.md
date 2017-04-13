---
title: "x:Class Directive | Microsoft Docs"
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
  - "x:Class"
  - "xClass"
  - "Class"
helpviewer_keywords: 
  - "Class attribute in XAML [XAML Services]"
  - "XAML [XAML Services], x:Class attribute"
  - "x:Class attribute [XAML Services]"
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 26
---
# x:Class Directive
Configura la compilación del marcado XAML para combinar clases parciales entre el marcado y el código subyacente.  La clase parcial de código se define en un archivo de código independiente en un lenguaje [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)], mientras que la clase parcial de marcado normalmente se crea mediante generación de código durante la compilación del código XAML.  
  
## Uso de atributos XAML  
  
```  
<object x:Class="namespace.classname"...>  
  ...  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`namespace`|Opcional.  Especifica un espacio de nombres [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] que contiene la clase parcial identificada por `classname`.  Si se especifica `namespace`, se incluye un punto \(.\) para separar `namespace` y `classname`.  Vea la sección Comentarios.|  
|`classname`|Obligatorio.  Especifica el nombre de [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] de la clase parcial que conecta el código XAML cargado y el código subyacente de ese código XAML.|  
  
## Dependencias  
 `x:Class` sólo se pueden especificar en el elemento raíz de una producción XAML.  `x:Class` no es válido en cualquier objeto que tenga un elemento primario en la producción XAML.  Para obtener más información, vea [\[MS\-XAML\] sección 4.3.1.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## Comentarios  
 El valor `namespace` puede contener puntos adicionales para organizar espacios de nombres relacionados en las jerarquías del nombre, que es una técnica común en programación en .NET Framework.  Solamente se interpreta el último punto de una cadena de valores `x:Class` para separar `namespace` y `classname.` La clase que se usa como `x:Class` no puede ser una clase anidada.  No se permiten clases anidadas porque determinar el significado de puntos para las cadenas `x:Class` sería ambiguo si se permitieran clases anidadas.  
  
 En los modelos de programación existentes que usan `x:Class`, `x:Class` es opcional en el sentido de que es completamente válido que haya una página XAML que no tenga absolutamente ningún código subyacente.  Sin embargo, esa capacidad básica interactúa con acciones de compilación como implementada por marcos que utilizan XAML.  La capacidad `x:Class` también está influenciada por los roles que diversas clasificaciones de contenido especificado por XAML tienen en un modelo de la aplicación de un marco y en las acciones de compilación correspondientes.  Si su XAML declara los valores de atributo del control de eventos o crea instancias de elementos personalizados donde las clases se definen en la clase de código subyacente, debe proporcionar la directiva de referencia `x:Class` \(o [x:Subclass](../../../docs/framework/xaml-services/x-subclass-directive.md)\) a la clase adecuada para el código subyacente.  
  
 El valor de la directiva `x:Class` debe ser una cadena que especifica el nombre completo de una clase pero sin ninguna información de ensamblado \(equivalente a <xref:System.Type.FullName%2A?displayProperty=fullName>\).  En las aplicaciones simples, se puede omitir la información de espacio de nombres CLR si el código subyacente también está estructurado de esa manera \(la definición de código se inicia en el nivel de clases\).  
  
 El archivo de código subyacente para una definición de página o de aplicación debe estar dentro de un archivo de código incluido como parte del proyecto que genera una aplicación compilada e implica la compilación del marcado.  Debe seguir las reglas de nomenclatura de las clases CLR.  Para obtener más información, vea [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md).  De forma predeterminada, la clase de código subyacente debe ser `public`; sin embargo, puede definirla en otro nivel de acceso mediante [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md).  
  
 Esta interpretación del atributo `x:Class` se aplica solamente a una implementación de XAML basada en CLR, en particular para los servicios XAML de .NET Framework.  Otras implementaciones de XAML que no se basan en CLR y no usan las clases de servicios XAML de .NET Framework, podrían usar una fórmula de resolución diferente para conectar el marcado XAML y el código en tiempo de ejecución de respaldo.  Para obtener más información acerca de interpretaciones más generales de `x:Class`, vea [\[MS\-XAML\]](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 En cierto nivel de arquitectura, el significado de `x:Class` está sin definir en los servicios XAML de .NET Framework.  Esto es debido a que los servicios XAML de .NET Framework no especifica el modelo de programación por el que el marcado XAML y el código de respaldo están conectados.  Los marcos concretos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML y el código subyacente basado en CLR, podrían aplicar usos adicionales de la directiva `x:Class`.  Cada marco puede tener sus propias acciones de compilación que habilitan algunos de los comportamientos o componentes concretos que se deben incluir en el entorno de compilación.  Dentro de un marco, las acciones de compilación también pueden variar dependiendo del lenguaje de CLR concreto que se utiliza para el código subyacente.  
  
## x:Clase en el modelo de programación de WPF  
 En las aplicaciones de WPF y el modelo de aplicaciones de WPF, `x:Class` se puede declarar como un atributo para cualquier elemento que sea la raíz de un archivo XAML y se haya compilando \(el código XAML se ha incluido en un proyecto de aplicación de WPF con la acción de compilación `Page`\), o para la raíz <xref:System.Windows.Application> en la definición de una aplicación de WPF compilada.  Si se declara `x:Class` en cualquier elemento que no sea una raíz de página o raíz de aplicación, o en un archivo XAML de WPF que no esté compilado, se producirá un error en tiempo de compilación en el compilador XAML de WPF en [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] y [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)].  Para obtener información sobre otros aspectos del control `x:Class` en WPF, vea [Código subyacente y XAML en WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
## x:Class para Windows Workflow Foundation  
 Para Windows Workflow Foundation, `x:Class` asigna un nombre a la clase de una actividad personalizada compuesta completamente en XAML o asigna nombre a la clase parcial de la página XAML para un diseñador de actividades con código subyacente.  
  
## Notas de uso de Silverlight  
 `x:Class` para Silverlight se documenta por separado.  Para obtener más información, vea [Características de lenguaje \(x:\) de espacios de nombres XAML \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## Vea también  
 [x:Subclass Directive](../../../docs/framework/xaml-services/x-subclass-directive.md)   
 [Clases XAML y personalizadas para WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)