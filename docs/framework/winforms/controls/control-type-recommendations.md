---
title: Recomendaciones sobre tipos de controles
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: 5e3337dddcc39517558cf85af76223306d20d2bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599704"
---
# <a name="control-type-recommendations"></a>Recomendaciones sobre tipos de controles
.NET Framework ofrece la posibilidad de desarrollar e implementar nuevos controles. Además de los controles de usuario conocidos, verá que ahora puede escribir controles personalizados que realizan su propia representación y que incluso pueden ampliar la funcionalidad de los controles existentes mediante herencia. Decidir qué tipo de control va a crear puede resultar confuso. En esta sección se indican las diferencias entre los distintos tipos de controles de los que puede heredar, y ofrece consideraciones sobre el tipo que deberá elegir para su proyecto.  
  
> [!NOTE]
>  Si desea crear un control para usarlo en formularios Web Forms, consulte [Desarrollar controles de servidor de ASP.NET personalizados](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
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
  
-   [Cómo: Mostrar un Control en la elija el cuadro de diálogo de elementos de cuadro de herramientas](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [Tutorial: Heredar de un Control de Windows Forms con VisualC#](https://msdn.microsoft.com/library/5h0k2e6x\(v=vs.110\))  
  
-   [Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un Control](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Cómo: Heredar de Windows existente controles de formularios](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Cómo: Heredar de la clase de Control](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [Cómo: Alinear un Control con los bordes de formularios en tiempo de diseño](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Cómo: Heredar de la clase UserControl](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Cómo: Crear controles de Windows Forms](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Cómo: Crear controles compuestos](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Tutorial: Crear un Control compuesto con Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Tutorial: Crear un Control compuesto con VisualC#](https://msdn.microsoft.com/library/a6h7e207\(v=vs.110\))  
  
-   [Tutorial: Heredar de un Control de Windows Forms con Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Cómo: Crear un Control de Windows Forms que aproveche las características en tiempo de diseño](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Cómo: Crear un Control de Windows Forms que aproveche las características en tiempo de diseño](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## <a name="see-also"></a>Vea también
- [Cómo: Desarrollar un Control de formularios de Windows Simple](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)
- [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
