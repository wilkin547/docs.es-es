---
title: "Crear y utilizar componentes en Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "componentes [Visual Basic]"
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Crear y utilizar componentes en Visual Basic
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un *componente* es una clase que implementa la interfaz <xref:System.ComponentModel.IComponent?displayProperty=fullName> o se deriva directa o indirectamente de una clase que implementa <xref:System.ComponentModel.IComponent>.  Un componente de [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)] es un objeto que es reutilizable, puede interactuar con otros objetos y proporciona control sobre recursos externos y compatibilidad en tiempo de diseño.  
  
 Una característica importante de los componentes es que se pueden diseñar, lo que significa que una clase que constituye un componente se puede utilizar en el entorno de desarrollo integrado \(IDE\) de [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)].  Un componente se puede agregar al cuadro de herramientas, se puede arrastrar y colocar en un formulario y manipularse en una superficie de diseño.  Observe que [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)] incorpora compatibilidad en tiempo de diseño con los componentes; un desarrollador de componentes no tiene que realizar ningún trabajo adicional para aprovechar la funcionalidad base en tiempo de diseño.  
  
 Un *control* es similar a un componente, ya que ambos se pueden diseñar.  Sin embargo, un control proporciona una interfaz de usuario, mientras que un componente no.  Un control debe derivarse de una de las clases de control base: <xref:System.Windows.Forms.Control> o <xref:System.Web.UI.Control>.  
  
## Cuándo crear un componente  
 Si la clase se va a utilizar en una superficie de diseño \(como los Windows Forms o el Diseñador de formularios Web Forms\) pero no tiene una interfaz de usuario, debe ser un componente e implementar la interfaz <xref:System.ComponentModel.IComponent> o derivarse de una clase que implemente directa o indirectamente la interfaz <xref:System.ComponentModel.IComponent>.  
  
 Las clases <xref:System.ComponentModel.Component> y <xref:System.ComponentModel.MarshalByValueComponent> son implementaciones base de la interfaz <xref:System.ComponentModel.IComponent>.  La diferencia principal entre estas clases es que las referencias de la clase <xref:System.ComponentModel.Component> se calculan por referencia, mientras que las de <xref:System.ComponentModel.IComponent> se calculan por valor.  La siguiente lista incluye exhaustivas instrucciones para los implementadores.  
  
-   Si las referencias de su componente tienen que calcularse por referencia, derívelo de <xref:System.ComponentModel.Component>.  
  
-   Si las referencias de su componente tienen que calcularse por valor, derívelo de <xref:System.ComponentModel.MarshalByValueComponent>.  
  
-   Si su componente no se puede derivar de una de las implementaciones base debido a la herencia única, implemente la interfaz <xref:System.ComponentModel.IComponent>.  
  
 Para obtener más información sobre la compatibilidad en tiempo de diseño, vea [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md) y [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md).  
  
## Clases de componentes  
 El espacio de nombres <xref:System.ComponentModel> proporciona clases que se utilizan para implementar el comportamiento de componentes y controles en tiempo de diseño y en tiempo de ejecución.  Este espacio de nombres incluye las clases e interfaces necesarias para implementar atributos, convertidores de tipos, enlaces a orígenes de datos y componentes de licencia.  
  
 Las clases de componente básicas son:  
  
-   <xref:System.ComponentModel.Component>.  Implementación base de la interfaz <xref:System.ComponentModel.IComponent>.  Esta clase habilita el uso compartido de objetos entre las aplicaciones.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>.  Implementación base de la interfaz <xref:System.ComponentModel.IComponent>.  
  
-   <xref:System.ComponentModel.Container>.  Implementación base de la interfaz <xref:System.ComponentModel.IContainer>.  Esta clase encapsula cero o más componentes.  
  
 Algunas de las clases que se utilizan para otorgar licencias de componentes son:  
  
-   <xref:System.ComponentModel.License>.  Clase base abstracta de todas las licencias.  Una licencia se concede a una instancia concreta de un componente.  
  
-   <xref:System.ComponentModel.LicenseManager>.  Proporciona propiedades y métodos para agregar una licencia a un componente y administrar un <xref:System.ComponentModel.LicenseProvider>.  
  
-   <xref:System.ComponentModel.LicenseProvider>.  Clase base abstracta para implementar un proveedor de licencias.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>.  Especifica la clase <xref:System.ComponentModel.LicenseProvider> que se usa con una clase.  
  
 Clases normalmente utilizadas para describir y conservar componentes.  
  
-   <xref:System.ComponentModel.TypeDescriptor>.  Proporciona información sobre las características de un componente, como sus atributos, propiedades y eventos.  
  
-   <xref:System.ComponentModel.EventDescriptor>.  Proporciona información sobre un evento.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>.  Proporciona información sobre una propiedad.  
  
## Secciones relacionadas  
 [Class vs. Component vs. Control](../Topic/Class%20vs.%20Component%20vs.%20Control.md)  
 Define *componente* y *control* y describe las diferencias entre ellos y las clases.  
  
 [Component Authoring](../Topic/Component%20Authoring.md)  
 Guía de orientación para comenzar a utilizar componentes.  
  
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)  
 Vínculos a temas que proporcionan instrucciones paso a paso para la programación de componentes.  
  
 [Component Classes](../Topic/Component%20Classes.md)  
 Describe qué convierte una clase en un componente, formas de exponer la funcionalidad de los componentes, cómo controlar el acceso a los componentes y cómo controlar el modo en que se crean instancias de componentes.  
  
 [Solución de problemas relacionados con la creación de controles y componentes](../Topic/Troubleshooting%20Control%20and%20Component%20Authoring.md)  
 Explica cómo resolver problemas comunes.  
  
## Vea también  
 [How to: Access Design\-Time Support in Windows Forms](../Topic/How%20to:%20Access%20Design-Time%20Support%20in%20Windows%20Forms.md)   
 [How to: Extend the Appearance and Behavior of Controls in Design Mode](../Topic/How%20to:%20Extend%20the%20Appearance%20and%20Behavior%20of%20Controls%20in%20Design%20Mode.md)   
 [How to: Perform Custom Initialization for Controls in Design Mode](../Topic/How%20to:%20Perform%20Custom%20Initialization%20for%20Controls%20in%20Design%20Mode.md)