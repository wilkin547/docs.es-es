---
title: "Desarrollar controles de formularios Windows Forms en tiempo de dise&#241;o | Microsoft Docs"
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
  - "Controles de Windows Forms"
  - "Controles de formularios Windows Forms, crear"
  - "controles [Windows Forms]"
  - "controles [Windows Forms], crear"
  - "controles de usuario [Windows Forms]"
  - "controles personalizados [Windows Forms]"
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Desarrollar controles de formularios Windows Forms en tiempo de dise&#241;o
Para los autores de controles, .NET Framework proporciona una gran cantidad de tecnología de creación de controles. Los creadores ya no están limitados al diseño de controles compuestos que actúan como una colección de controles preexistentes. A través de la herencia, puede crear sus propios controles de controles compuestos preexistentes o controles de formularios Windows Forms preexistentes. También puede diseñar sus propios controles que implementen el dibujo personalizado. Estas opciones permiten una gran flexibilidad en el diseño y la funcionalidad de la interfaz visual. Para aprovechar estas características, debe estar familiarizado con conceptos de programación basado en objetos.  
  
> [!NOTE]
>  No es necesario tener un conocimiento exhaustivo de herencia, pero le resultará útil para hacer referencia a [NOT IN BUILD: herencia en Visual Basic](http://msdn.microsoft.com/es-es/e5e6e240-ed31-4657-820c-079b7c79313c).  
  
 Si desea crear controles personalizados para utilizarlos en formularios Web Forms, vea [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Tutorial: Crear un Control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Muestra cómo crear un control compuesto simple en Visual Basic.  
  
 [Tutorial: Crear un Control compuesto con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Muestra cómo crear un control compuesto simple en C#.  
  
 [Tutorial: Heredar de un Control de formularios Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Muestra cómo crear un control de formularios Windows Forms sencillo utilizando la herencia en Visual Basic.  
  
 [Tutorial: Heredar de un Control de formularios Windows Forms con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Muestra cómo crear un control de formularios Windows Forms sencillo utilizando la herencia en C#.  
  
 [Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en Windows Forms controles](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Muestra cómo usar la característica de etiquetas inteligentes en controles de formularios Windows Forms.  
  
 [Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 Muestra cómo utilizar el <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=fullName> atributo para serializar una colección.  
  
 [Tutorial: Depurar personalizado controles Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Muestra cómo depurar el comportamiento en tiempo de diseño de un control de formularios Windows Forms.  
  
 [Tutorial: Crear un Control de Windows Forms que aproveche las características de tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 Muestra cómo integrar un control compuesto en el entorno de diseño.  
  
 [Cómo: crear controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Proporciona información general sobre consideraciones para implementar un control de formularios Windows Forms.  
  
 [Cómo: crear controles compuestos](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 Muestra cómo crear un control mediante la herencia de un control compuesto.  
  
 [Cómo: heredar de la clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 Proporciona información general sobre el procedimiento para crear un control compuesto.  
  
 [Cómo: heredar de Windows existentes controles de formularios](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 Muestra cómo crear un control extendido heredando de la <xref:System.Windows.Forms.Button> clase del control.  
  
 [Cómo: heredar de la clase de Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 Proporciona información general de la creación de un control extendido.  
  
 [Cómo: alinear un Control con los bordes de formularios en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Muestra cómo utilizar el <xref:System.Windows.Forms.Control.Dock%2A> propiedad para alinear el control con el borde del formulario que ocupa.  
  
 [Cómo: mostrar un Control en el cuadro de diálogo de elementos de cuadro de herramientas elegir](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Muestra el procedimiento para instalar el control para que aparezca en el **Personalizar cuadro de herramientas** cuadro de diálogo.  
  
 [Cómo: proporcionar un mapa de bits del cuadro de herramientas para un Control](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Muestra cómo utilizar el <xref:System.Drawing.ToolboxBitmapAttribute> para mostrar un icono junto al control personalizado en el **cuadro de herramientas**.  
  
 [Cómo: probar el comportamiento de tiempo de ejecución de un control de usuario](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Muestra cómo utilizar el **UserControl Test Container** para probar el comportamiento de un control compuesto.  
  
 [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Explica el significado y el uso de la lista de errores de tiempo de diseño que aparece en Microsoft Visual Studio cuando no se puede cargar el Diseñador de formularios Windows Forms.  
  
 [Solución de problemas de creación de controles y componentes](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Muestra cómo diagnosticar y corregir los problemas comunes que pueden producirse al crear un componente personalizado o un control.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Control?displayProperty=fullName>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Desarrollo personalizado de Windows Forms controles con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 Describe cómo crear sus propios controles personalizados con .NET Framework.  
  
 [Independencia del lenguaje y componentes independientes del lenguaje](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 Presenta common language runtime, que está diseñado para simplificar la creación y uso de componentes. Un aspecto importante de esta simplificación es mejoras de interoperabilidad entre componentes escritos con diferentes lenguajes de programación. Common Language Specification (CLS) hace posible crear herramientas y componentes que funcionen con varios lenguajes de programación.  
  
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Describe cómo habilitar el componente o el control se mostrará en el **Personalizar cuadro de herramientas** cuadro de diálogo.