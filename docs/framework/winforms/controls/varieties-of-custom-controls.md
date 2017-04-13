---
title: "Variedades de controles personalizados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles compuestos"
  - "controles [Windows Forms], compuestos"
  - "controles [Windows Forms], extendidos"
  - "controles [Windows Forms], tipos de"
  - "controles [Windows Forms], controles de usuario"
  - "controles personalizados [Windows Forms]"
  - "controles extendidos"
  - "controles de usuario [Windows Forms]"
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Variedades de controles personalizados
Con .NET Framework, se pueden desarrollar e implementar nuevos controles.  Se puede ampliar la funcionalidad de los conocidos controles de usuario así como de los controles existentes por medio de la herencia.  También se pueden escribir controles personalizados que realizan su propia representación.  
  
 La decisión sobre qué tipo de control se va a crear puede ser difícil.  En este tema se destacan las diferencias entre las distintas clases de controles desde los que se puede heredar, y se proporciona información sobre cómo elegir una determinada clase de control para el proyecto.  
  
> [!NOTE]
>  Para obtener información sobre cómo crear un control para utilizarlo en formularios Web Forms, vea [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
  
## Clase de control base  
 La clase <xref:System.Windows.Forms.Control> es la clase base para los controles de formularios Windows Forms.  Proporciona la infraestructura necesaria para la presentación visual de las aplicaciones de Windows Forms.  
  
 La clase <xref:System.Windows.Forms.Control> realiza las tareas siguientes para proporcionar la presentación visual de las aplicaciones de Windows Forms:  
  
-   Expone un controlador de ventanas.  
  
-   Administra el enrutamiento de mensajes.  
  
-   Proporciona eventos del mouse y del teclado y muchos otros eventos de la interfaz de usuario.  
  
-   Proporciona características de diseño avanzadas.  
  
-   Contiene muchas propiedades específicas a la presentación visual, como <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A> y <xref:System.Windows.Forms.Control.Width%2A>.  
  
-   Proporciona la seguridad y compatibilidad para subprocesos necesarias para que un control de formularios Windows Forms actúe como un control de Microsoft® ActiveX®.  
  
 Dado que gran parte de la infraestructura la proporciona la clase base, resulta relativamente fácil desarrollar controles de formularios Windows Forms propios.  
  
## Tipos de controles  
 Los formularios Windows Forms admiten tres tipos de controles definidos por el usuario: *compuesto*, *ampliado* y *personalizado*.  En las secciones siguientes se describe cada tipo de control y se dan recomendaciones para elegir el tipo que puede utilizar en sus proyectos.  
  
### Controles compuestos  
 Un control compuesto es una colección de controles de formularios Windows Forms encapsulados en un contenedor común.  Este tipo de control a veces se denomina *control de usuario*.  Los controles contenidos se denominan *controles constituyentes*.  
  
 El control compuesto conserva toda la funcionalidad inherente asociada a cada uno de los controles de formularios Windows Forms contenidos y permite exponer y enlazar sus propiedades de forma selectiva.  El control compuesto también proporciona gran cantidad de funcionalidad de control de teclado predeterminada sin ningún esfuerzo adicional de desarrollo por su parte.  
  
 Por ejemplo, se puede compilar un control compuesto para mostrar los datos relacionados con la dirección del cliente desde una base de datos.  Este control puede incluir un control <xref:System.Windows.Forms.DataGridView> para mostrar los campos de la base de datos, un <xref:System.Windows.Forms.BindingSource> para controlar el enlace a un origen de datos y un control <xref:System.Windows.Forms.BindingNavigator> para moverse por los registros.  Podría exponer las propiedades de enlace de datos de forma selectiva y podría empaquetar y reutilizar todo el control de una aplicación a otra.  Para obtener un ejemplo de este tipo de control compuesto, vea [Cómo: Aplicar atributos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Para crear un control compuesto, derive de la clase <xref:System.Windows.Forms.UserControl>.  La clase base <xref:System.Windows.Forms.UserControl> proporciona enrutamiento de teclado a los controles secundarios permitiéndoles trabajar como grupo.  Para obtener más información, vea [Desarrollar un control de formularios Windows Forms compuesto](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
 **Recomendación**  
  
 Herede de la clase <xref:System.Windows.Forms.UserControl> si:  
  
-   Desea combinar la funcionalidad de varios controles de formularios Windows Forms en una sola unidad reutilizable.  
  
### Controles ampliados  
 Puede derivar un control heredado de cualquier control existente de formularios Windows Forms.  Este método permite conservar toda la funcionalidad inherente a un control de formularios Windows Forms y, a continuación, ampliarla agregando propiedades, métodos y otras características personalizadas.  Esta opción permite reemplazar la lógica de representación del control base y, a continuación, extender la interfaz de usuario cambiando su apariencia.  
  
 Por ejemplo, puede crear un control derivado del control <xref:System.Windows.Forms.Button> que controle el número de veces que el usuario ha hecho clic en él.  
  
 En algunos controles, también es posible agregar una apariencia personalizada a la interfaz gráfica del control; para ello, deberá reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base.  Para crear un botón ampliado que controla el número de clics, reemplace el método <xref:System.Windows.Forms.Control.OnPaint%2A> para llamar a la implementación base de <xref:System.Windows.Forms.Control.OnPaint%2A>, y luego representar el contador de clics en una esquina del área de cliente del control <xref:System.Windows.Forms.Button>.  
  
 **Recomendación**  
  
 Herede de un control de formularios Windows Forms si:  
  
-   La mayor parte de la funcionalidad necesaria es ya idéntica a la de un control de formularios Windows Forms existente.  
  
-   No necesita una interfaz gráfica de usuario personalizada o desea diseñar una nueva interfaz gráfica de usuario para un control existente.  
  
### Controles personalizados  
 Otra forma de crear un control consiste en crear uno prácticamente desde el principio mediante la herencia de <xref:System.Windows.Forms.Control>.  La clase <xref:System.Windows.Forms.Control> proporciona toda la funcionalidad básica que requieren los controles, incluso los eventos de control del teclado y del mouse, pero no proporciona una funcionalidad ni una interfaz gráfica específicas para el control.  
  
 Crear un control mediante la herencia de la clase <xref:System.Windows.Forms.Control> requiere mucho más esfuerzo que heredar de <xref:System.Windows.Forms.UserControl> o de un control de formularios Windows Forms existente.  Como debe realizar mucha implementación, el control puede tener una mayor flexibilidad que un control compuesto o ampliado, lo que permite crear controles a medida para que se ajusten exactamente a las necesidades.  
  
 Para implementar un control personalizado, debe escribir el código para el evento <xref:System.Windows.Forms.Control.OnPaint%2A> del control, así como cualquier código específico de la característica que necesita.  También puede reemplazar el método <xref:System.Windows.Forms.Control.WndProc%2A> y controlar directamente los mensajes de ventanas.  Éste es el modo más eficaz de crear un control, pero para utilizar esta técnica con eficacia, necesita estar familiarizado con la API de Microsoft Win32®.  
  
 Un ejemplo de control personalizado es un control de reloj que duplique la apariencia y el comportamiento de un reloj analógico.  Sería necesario invocar una representación personalizada para hacer que las manecillas de reloj se movieran en respuesta a eventos <xref:System.Windows.Forms.Timer.Tick> procedentes de un componente <xref:System.Windows.Forms.Timer> interno.  Para obtener más información, vea [Cómo: Desarrollar un control de formularios Windows Forms sencillo](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 **Recomendación**  
  
 Herede de la clase <xref:System.Windows.Forms.Control> si:  
  
-   Desea proporcionar una representación gráfica personalizada del control.  
  
-   Necesita implementar funcionalidad personalizad que no se encuentre disponible por medio de controles estándar.  
  
### Controles ActiveX  
 Aunque la infraestructura de los formularios Windows Forms se ha optimizado para que hospeden controles de formularios Windows Forms, puede seguir utilizando controles ActiveX.  Visual Studio ofrece compatibilidad para esta tarea.  Para obtener más información, vea [Cómo: Agregar controles ActiveX a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md).  
  
### Controles sin ventana  
 Las tecnologías de Microsoft Visual Basic® 6.0 y ActiveX admiten los controles *sin ventana*.  Los controles sin ventana no se admiten en los formularios Windows Forms.  
  
## Experiencia de diseño personalizada  
 Si se necesita implementar una experiencia personalizada en tiempo de diseño, puede crear a su propio diseñador.  Para los controles compuestos, derive la clase de diseñador personalizada de las clases <xref:System.Windows.Forms.Design.ParentControlDesigner> o <xref:System.Windows.Forms.Design.DocumentDesigner>.  Para los controles ampliados y personalizados, derive la clase de diseñador personalizada de la clase <xref:System.Windows.Forms.Design.ControlDesigner>.  
  
 Utilice <xref:System.ComponentModel.DesignerAttribute> para asociar el control al diseñador.  Para obtener más información, vea [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md) y [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md).  
  
## Vea también  
 [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Cómo: Desarrollar un control de formularios Windows Forms sencillo](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)   
 [Desarrollar un control de formularios Windows Forms compuesto](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)