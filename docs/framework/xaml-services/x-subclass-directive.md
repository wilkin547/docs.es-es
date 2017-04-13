---
title: "x:Subclass Directive | Microsoft Docs"
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
  - "Subclass"
  - "xSubclass"
  - "x:Subclass"
helpviewer_keywords: 
  - "x:Subclass attribute [XAML Services]"
  - "XAML [XAML Services], x:Subclass attribute"
  - "Subclass attribute in XAML [XAML Services]"
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Subclass Directive
Modifica el comportamiento de compilación del marcado XAML si se proporciona también `x:Class`.  En lugar de crear una clase parcial basada en la clase `x:Class`, el atributo `x:Class` proporcionado se crea como una clase intermedia, por lo que se espera que la clase derivada proporcionada se base en `x:Class`.  
  
## Uso de atributos XAML  
  
```  
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">  
   ...  
</object>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`namespace`|Opcional.  Especifica un espacio de nombres CLR que contiene `classname`.  Si se especifica `namespace`, se incluye un punto \(.\) para separar `namespace` y `classname`.|  
|`classname`|Obligatorio.  Especifica el nombre CLR de la clase parcial que conecta el XAML cargado y el código subyacente de ese XAML.  Vea la sección Comentarios.|  
|`subclassNamespace`|Opcional.  Puede ser diferente de `namespace` si cada espacio de nombres puede resolver el otro.  Especifica un espacio de nombres CLR que contiene `subclassName`.  Si se especifica `subclassName`, se incluye un punto \(.\) para separar `subclassNamespace` y `subclassName`.|  
|`subclassName`|Obligatorio.  Especifica el nombre CLR de la subclase.|  
  
## Dependencias  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) también se debe proporcionar en el mismo objeto, y ese objeto debe ser el elemento raíz de la producción XAML.  
  
## Comentarios  
 El uso de `x:Subclass` está destinado principalmente a los lenguajes que no admiten las declaraciones de clases parciales.  
  
 La clase utilizada cuando `x:Subclass` no pueden ser una clase anidada y `x:Subclass` debe hacer referencia al objeto raíz como se explica en la sección "Dependencias".  
  
 De lo contrario, el significado conceptual de `x:Subclass` está sin definir a través de la implementación de los servicios XAML de .NET Framework.  Esto es debido a que el comportamiento de los servicios XAML de .NET Framework no especifica el modelo de programación total por el que el marcado XAML y el código de respaldo están conectados.  Los marcos concretos que usan modelos de programación o modelos de aplicación para definir cómo conectar el marcado XAML, marcado compilado y el código subyacente basado en CLR, realizan implementaciones de conceptos más extensos relacionada con `x:Class` y `x:Subclass`.  Cada marco podría tener sus propias acciones de compilación que habilitan algunos de los comportamientos o componentes concretos que se deben incluir en el entorno de compilación.  Dentro de un marco, las acciones de compilación también pueden variar dependiendo del lenguaje de CLR concreto que se utiliza para el código subyacente.  
  
## Notas de uso de WPF  
 `x:Subclass` pueden estar en una raíz de la página o en la raíz <xref:System.Windows.Application> de la definición de aplicación, que ya tiene `x:Class`.  Si se declara `x:Subclass` en cualquier elemento que no sea la raíz de una página o aplicación, o se especifica sin que exista `x:Class`, se producirá un error en tiempo de compilación.  
  
 La creación de clases derivadas que funcionen correctamente para el escenario `x:Subclass` es una tarea bastante compleja.  Puede que sea necesario examinar los archivos intermedios \(los archivos .g generados en la carpeta obj del proyecto mediante la compilación de marcado, con nombres que incorporan los nombres de los archivos .xaml\).  Estos archivos intermedios pueden ayudarle a determinar el origen de algunas construcciones de programación en las clases parciales combinadas de la aplicación compilada.  
  
 Los controladores de eventos de la clase derivada deben ser de tipo `internal override` \(`Friend Overrides` en [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]\), a fin de invalidar los códigos auxiliares correspondientes a los controladores que se crean en la clase intermedia durante la compilación.  De lo contrario, las implementaciones de la clase derivada ocultarían la implementación de clase intermedia \(prevalecerían sobre ella\) y no se invocan los controladores de clase intermedios.  
  
 Al definir `x:Class` y `x:Subclass`, no es preciso proporcionar ninguna implementación de la clase a la que `x:Class` hace referencia.  Únicamente hay que darle un nombre mediante el atributo `x:Class`, para que sirva de guía al compilador en relación con la clase que se crea en los archivos intermedios \(el compilador no selecciona un nombre predeterminado en este caso\).  Puede dar una implementación a la clase `x:Class`; sin embargo, este no es el escenario típico para usar tanto `x:Class` como `x:Subclass`.  
  
## Vea también  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Clases XAML y personalizadas para WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)