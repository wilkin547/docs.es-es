---
title: Recomendaciones sobre tipos de controles
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: 5dc734997917af7ec4a20a6c12ae04825507c7ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098460"
---
# <a name="control-type-recommendations"></a>Recomendaciones sobre tipos de controles
.NET Framework ofrece la posibilidad de desarrollar e implementar nuevos controles. Además de los controles de usuario conocidos, verá que ahora puede escribir controles personalizados que realizan su propia representación y que incluso pueden ampliar la funcionalidad de los controles existentes mediante herencia. Decidir qué tipo de control va a crear puede resultar confuso. En esta sección se indican las diferencias entre los distintos tipos de controles de los que puede heredar, y ofrece consideraciones sobre el tipo que deberá elegir para su proyecto.  
  
> [!NOTE]
>  Si desea crear un control para usarlo en formularios Web Forms, consulte [Desarrollar controles de servidor de ASP.NET personalizados](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).  
  
## <a name="inheriting-from-a-windows-forms-control"></a>Heredar de un control de Windows Forms  
 Puede derivar un control heredado de cualquier control de Windows Forms existente. Este enfoque permite conservar toda la funcionalidad inherente de un control de Windows Forms y, después, ampliarla agregando propiedades, métodos u otras funcionalidades personalizadas. Por ejemplo, podría crear un control derivado de <xref:System.Windows.Forms.TextBox> que solo admita números y que convierta automáticamente la entrada en un valor. Este tipo de control podría contener código de validación al que se llama cada vez que cambia el texto del cuadro de texto, y podría tener una propiedad adicional, Value. En algunos controles, también puede agregar una apariencia personalizada a la interfaz gráfica del control invalidando el método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base.  
  
 Herede de un control de Windows Forms si:  
  
-   La mayor parte de la funcionalidad que necesita es idéntica a la de un control de Windows Forms existente.  
  
-   No necesita una interfaz gráfica personalizada o quiere diseñar un nuevo front-end gráfico para un control existente.  
  
## <a name="inheriting-from-the-usercontrol-class"></a>Heredar de la clase UserControl  
 Un control de usuario es una colección de controles de Windows Forms encapsulados en un contenedor común. El contenedor conserva toda la funcionalidad inherente asociada a cada uno de los controles de Windows Forms y permite exponer y enlazar sus propiedades de forma selectiva. Un ejemplo de un control de usuario podría ser un control creado para mostrar los datos de dirección de los clientes de una base de datos. Este control incluiría varios cuadros de texto para mostrar cada campo y los controles de botón para navegar por los registros. Las propiedades de enlace de datos se podrían exponer de forma selectiva y el control completo se podría empaquetar y reutilizar en distintas aplicaciones.  
  
 Herede de la clase <xref:System.Windows.Forms.UserControl> si:  
  
-   Quiere combinar la funcionalidad de varios controles de Windows Forms en una sola unidad reutilizable.  
  
## <a name="inheriting-from-the-control-class"></a>Heredar de la clase Control  
 Otra forma de crear un control consiste en crear uno prácticamente desde el principio heredando de <xref:System.Windows.Forms.Control>. La clase <xref:System.Windows.Forms.Control> proporciona toda la funcionalidad básica requerida por los controles (por ejemplo, los eventos), pero ninguna funcionalidad específica del control ni la interfaz gráfica. Crear un control heredando de la clase <xref:System.Windows.Forms.Control> requiere mucho más esfuerzo que heredar de un control de usuario o de un control de Windows Forms existente. El autor debe escribir código para el evento <xref:System.Windows.Forms.Control.OnPaint%2A> del control, así como código para cualquier funcionalidad específica que se necesite. Sin embargo, permite una mayor flexibilidad y puede a adaptar un control a sus necesidades exactas. Un ejemplo de un control personalizado es un control de reloj que reproduce la apariencia y el funcionamiento de un reloj analógico. Sería necesario invocar una representación personalizado para hacer que las manecillas del reloj se movieran en respuesta a los eventos <xref:System.Windows.Forms.Timer.Tick> de un componente de temporizador interno.  
  
 Herede de la clase <xref:System.Windows.Forms.Control> si:  
  
-   Quiere proporcionar una representación gráfica personalizada del control.  
  
-   Necesita implementar funcionalidad personalizada que no está disponible en los controles estándar.  
  
-   [Filtrar para mostrar un control en el cuadro de diálogo Elegir elementos del cuadro de herramientas](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
  
-   [Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [Tutorial: Heredar de un control de formularios Windows Forms con Visual C#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
  
-   [Filtrar para proporcionar un mapa de bits del cuadro de herramientas para un control](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
  
-   [Filtrar para heredar de controles de formularios Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)  
  
-   [Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
  
-   [Filtrar para heredar de la clase Control](how-to-inherit-from-the-control-class.md)  
  
-   [Filtrar para comprobar el comportamiento de UserControl en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [Filtrar para alinear un control con los bordes de los formularios en tiempo de diseño](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
  
-   [Filtrar para heredar de la clase UserControl](how-to-inherit-from-the-usercontrol-class.md)  
  
-   [Filtrar para crear controles de formularios Windows Forms](how-to-author-controls-for-windows-forms.md)  
  
-   [Filtrar para crear controles compuestos](how-to-author-composite-controls.md)  
  
-   [Tutorial: Crear un control compuesto con Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
  
-   [Tutorial: Crear un control compuesto con Visual C#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
  
-   [Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
  
-   [Tutorial: Crear un control de formularios Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md)  
  
-   [Filtrar Crear un Control de Windows Forms que aproveche las características en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))  
  
## <a name="see-also"></a>Vea también

- [Filtrar para desarrollar un control sencillo de formularios Windows Forms](how-to-develop-a-simple-windows-forms-control.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
