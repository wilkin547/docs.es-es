---
title: Recomendaciones sobre tipos de controles
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a5996c398e4f864da4b505020974307b0e0e316
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="control-type-recommendations"></a>Recomendaciones sobre tipos de controles
.NET Framework ofrece la posibilidad de desarrollar e implementar nuevos controles. Además de los controles de usuario conocidos, verá que ahora puede escribir controles personalizados que realizan su propia representación y que incluso pueden ampliar la funcionalidad de los controles existentes mediante herencia. Decidir qué tipo de control va a crear puede resultar confuso. En esta sección se indican las diferencias entre los distintos tipos de controles de los que puede heredar, y ofrece consideraciones sobre el tipo que deberá elegir para su proyecto.  
  
> [!NOTE]
>  Si desea crear un control para usarlo en formularios Web Forms, consulte [Desarrollar controles de servidor de ASP.NET personalizados](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
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
  
-   [Cómo: Mostrar un control en el cuadro de diálogo Seleccionar elementos del cuadro de herramientas](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))  
  
-   [Tutorial: Heredar de un control de Windows Forms con Visual C#](http://msdn.microsoft.com/en-us/library/5h0k2e6x\(v=vs.110\))  
  
-   [Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Cómo: Heredar de controles de Windows Forms existentes](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Cómo: Heredar de la clase control](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))  
  
-   [Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [cómo: Heredar de la clase UserControl](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Cómo: Crear controles para Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Cómo: Crear controles compuestos](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Tutorial: Crear un control compuesto con Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Tutorial: Crear un control compuesto con Visual C#](http://msdn.microsoft.com/en-us/library/a6h7e207\(v=vs.110\))  
  
-   [Tutorial: Heredar de un control de Windows Forms con Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Cómo: Crear un control de Windows Forms que aproveche las características de tiempo de diseño](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Cómo: Crear un control de Windows Forms que aproveche las características de tiempo de diseño](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un control de formularios Windows Forms sencillo](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
