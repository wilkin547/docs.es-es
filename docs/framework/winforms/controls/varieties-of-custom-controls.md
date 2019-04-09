---
title: Variedades de controles personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
ms.openlocfilehash: 765befcf88247e4b2101b13c4937352ba4b070fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170713"
---
# <a name="varieties-of-custom-controls"></a>Variedades de controles personalizados
.NET Framework permite desarrollar e implementar nuevos controles. Puede extender la funcionalidad del control de usuario ya conocida, así como de los controles existentes, mediante la herencia. También puede escribir controles personalizados que realicen su propia representación.  
  
 Decidir qué tipo de control va a crear puede resultar confuso. En este tema se destacan las diferencias entre los distintos tipos de controles de los que puede heredar, y proporciona información sobre cómo elegir un tipo de control determinado para el proyecto.  
  
> [!NOTE]
>  Para obtener información sobre cómo crear un control para usarlo en formularios Web Forms, consulte [Desarrollar controles de servidor de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).  
  
## <a name="base-control-class"></a>Clase base de Control  
 La <xref:System.Windows.Forms.Control> clase es la clase base para controles de formularios Windows Forms. Proporciona la infraestructura necesaria para la presentación visual en aplicaciones de Windows Forms.  
  
 La <xref:System.Windows.Forms.Control> clase realiza las tareas siguientes para proporcionar la presentación visual en aplicaciones de Windows Forms:  
  
-   Expone un identificador de ventana.  
  
-   Administra el enrutamiento de los mensajes.  
  
-   Proporciona eventos de teclado y mouse, y muchos otros eventos de interfaz de usuario.  
  
-   Proporciona características de diseño avanzadas.  
  
-   Contiene muchas propiedades específicas de presentación visual, como <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, y <xref:System.Windows.Forms.Control.Width%2A>.  
  
-   Proporciona la seguridad y la compatibilidad para subprocesos necesarias para un control de Windows Forms que actúa como un control de Microsoft® ActiveX®.  
  
 Dado que la clase base proporciona gran parte de la infraestructura, es relativamente fácil desarrollar sus propios controles de Windows Forms.  
  
## <a name="kinds-of-controls"></a>Tipos de controles  
 Windows Forms admite tres tipos de controles definidos por el usuario: *compuestos*, *extendidos* y *personalizados*. En las secciones siguientes se describe cada tipo de control y se ofrecen recomendaciones para elegir el tipo para utilizar en los proyectos.  
  
### <a name="composite-controls"></a>Controles compuestos  
 Un control compuesto es una colección de controles de Windows Forms encapsulados en un contenedor común. Este tipo de control se denomina a veces *control de usuario*. Los controles contenidos se denominan *controles constituyentes*.  
  
 El control compuesto conserva toda la funcionalidad inherente asociada a cada uno de los controles de Windows Forms contenidos, y permite exponer y enlazar sus propiedades de forma selectiva. Un control compuesto también proporciona gran parte de la funcionalidad predeterminada del teclado sin ningún esfuerzo de desarrollo adicional por su parte.  
  
 Un ejemplo de un control compuesto podría ser un control creado para mostrar los datos de dirección de los clientes de una base de datos. Este control puede incluir un <xref:System.Windows.Forms.DataGridView> control para mostrar los campos de la base de datos, un <xref:System.Windows.Forms.BindingSource> para controlar el enlace a un origen de datos y un <xref:System.Windows.Forms.BindingNavigator> control para desplazarse por los registros. Las propiedades de enlace de datos se podrían exponer de forma selectiva, y el control completo se podría empaquetar y reutilizar en distintas aplicaciones. Para obtener un ejemplo de este tipo de control compuesto, vea [Cómo: Aplicar atributos en controles de formularios Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Para crear un control compuesto, derive de la <xref:System.Windows.Forms.UserControl> clase. La <xref:System.Windows.Forms.UserControl> clase base proporciona enrutamiento de teclado para los controles secundarios y permite a los controles secundarios para que funcione como un grupo. Para obtener más información, vea [Desarrollar un control de formularios Windows Forms compuesto](developing-a-composite-windows-forms-control.md).  
  
 **Recomendación**  
  
 Herede de la clase <xref:System.Windows.Forms.UserControl> si:  
  
-   Quiere combinar la funcionalidad de varios controles de Windows Forms en una sola unidad reutilizable.  
  
### <a name="extended-controls"></a>Controles extendidos  
 Puede derivar un control heredado de cualquier control de Windows Forms existente. Este enfoque permite conservar toda la funcionalidad inherente de un control de Windows Forms y, después, ampliarla agregando propiedades, métodos u otras características personalizadas. Con esta opción, puede invalidar la lógica de dibujo del control base y, a continuación, cambiar la apariencia de la interfaz de usuario para extenderla.  
  
 Por ejemplo, puede crear un control derivado de la <xref:System.Windows.Forms.Button> control que realiza el seguimiento de cuántas veces un usuario haya hecho clic en él.  
  
 En algunos controles, también puede agregar una apariencia personalizada a la interfaz gráfica de usuario del control invalidando el <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base. Para un botón extendido que realiza el seguimiento de clics, puede invalidar el <xref:System.Windows.Forms.Control.OnPaint%2A> método para llamar a la implementación base de <xref:System.Windows.Forms.Control.OnPaint%2A>y, a continuación, dibuje el número de clics en una esquina de la <xref:System.Windows.Forms.Button> área cliente del control.  
  
 **Recomendación**  
  
 Herede de un control de Windows Forms si:  
  
-   La mayor parte de la funcionalidad que necesita es idéntica a la de un control de Windows Forms existente.  
  
-   No necesita una interfaz gráfica de usuario personalizada o quiere diseñar una nueva interfaz gráfica de usuario para un control existente.  
  
### <a name="custom-controls"></a>Controles personalizados  
 Otra forma de crear un control consiste en crear uno prácticamente desde el principio heredando de <xref:System.Windows.Forms.Control>. La <xref:System.Windows.Forms.Control> clase proporciona toda la funcionalidad básica requerida por controles, incluidos los mouse y teclado de control de eventos, pero ninguna funcionalidad específica del control o la interfaz gráfica.  
  
 Crear un control heredando de la <xref:System.Windows.Forms.Control> clase requiere mucho más esfuerzo que heredar <xref:System.Windows.Forms.UserControl> o un control Windows Forms existente. Como puede realizar gran parte de la implementación, el control puede tener mayor flexibilidad que un control compuesto o ampliado, y puede personalizar el control exactamente para sus necesidades.  
  
 Para implementar un control personalizado, debe escribir código para el <xref:System.Windows.Forms.Control.OnPaint%2A> eventos de control, así como cualquier código específico de la característica que necesita. También puede invalidar el <xref:System.Windows.Forms.Control.WndProc%2A> método y controle los mensajes de windows directamente. Esta es la manera más eficaz de crear un control, pero para utilizar esta técnica de forma eficaz, debe estar familiarizado con la API Win32 de Microsoft®.  
  
 Un ejemplo de un control personalizado es un control de reloj que reproduce la apariencia y el funcionamiento de un reloj analógico. Se invoca una representación personalizada para hacer que las manecillas del reloj se muevan en respuesta a <xref:System.Windows.Forms.Timer.Tick> eventos desde una instancia interna <xref:System.Windows.Forms.Timer> componente. Para obtener más información, vea [Cómo: Desarrollar un Control de formularios de Windows Simple](how-to-develop-a-simple-windows-forms-control.md).  
  
 **Recomendación**  
  
 Herede de la clase <xref:System.Windows.Forms.Control> si:  
  
-   Quiere proporcionar una representación gráfica personalizada del control.  
  
-   Necesita implementar funcionalidad personalizada que no está disponible en los controles estándar.  
  
### <a name="activex-controls"></a>Controles ActiveX  
 Aunque la infraestructura de Windows Forms se han optimizado para hospedar controles de Windows Forms, todavía puede utilizar los controles ActiveX. Visual Studio es compatible con esta tarea. Para obtener más información, vea [Cómo: Agregar controles ActiveX a formularios Windows](how-to-add-activex-controls-to-windows-forms.md).  
  
### <a name="windowless-controls"></a>Controles sin ventana  
 Las tecnologías de Microsoft Visual Basic® 6.0 y ActiveX admiten controles *sin ventanas*. Los controles sin ventana no se admiten en Windows Forms.  
  
## <a name="custom-design-experience"></a>Experiencia de diseño personalizada  
 Si necesita implementar una experiencia personalizada en tiempo de diseño, puede crear su propio diseñador. Para los controles compuestos, derive la clase de diseñador personalizada de la <xref:System.Windows.Forms.Design.ParentControlDesigner> o <xref:System.Windows.Forms.Design.DocumentDesigner> clases. Para los controles ampliados y personalizados, derive la clase de diseñador personalizada de la <xref:System.Windows.Forms.Design.ControlDesigner> clase.  
  
 Use el <xref:System.ComponentModel.DesignerAttribute> para asociar el control a su diseñador. Para obtener más información, consulte [ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)) y [Cómo: Crear un Control de Windows Forms que aproveche las características de tiempo de diseño de](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).  
  
## <a name="see-also"></a>Vea también

- [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)
- [Filtrar para desarrollar un control sencillo de formularios Windows Forms](how-to-develop-a-simple-windows-forms-control.md)
- [Desarrollar un control de formularios Windows Forms compuesto](developing-a-composite-windows-forms-control.md)
- [Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Filtrar Crear un Control de Windows Forms que aproveche las características en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))
