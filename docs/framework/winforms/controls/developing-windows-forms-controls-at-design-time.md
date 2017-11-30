---
title: "Desarrollar controles de formularios Windows Forms en tiempo de diseño"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4f9680bb64339f2f232793beb9c47a36c07aa4a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="developing-windows-forms-controls-at-design-time"></a>Desarrollar controles de formularios Windows Forms en tiempo de diseño
Para los autores de controles, .NET Framework proporciona una gran cantidad de tecnologías de creación de controles. Los creadores ya no están limitados al diseño de controles compuestos que actúan como una colección de controles preexistentes. A través de la herencia, puede crear sus propios controles a partir de controles compuestos preexistentes o de controles de Windows Forms preexistentes. También puede diseñar sus propios controles que implementen el dibujo personalizado. Estas opciones permiten una gran flexibilidad en el diseño y la funcionalidad de la interfaz visual. Para aprovechar estas características, debe estar familiarizado con conceptos de programación basada en objetos.  
  
> [!NOTE]
>  No es necesario tener un conocimiento exhaustivo de herencia, pero quizá le resulte útil para hacer referencia a [Fundamentos de la herencia (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Si quiere crear controles personalizados para usarlos en formularios Web Forms, consulte [Desarrollar controles de servidor ASP.NET personalizados](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
## <a name="in-this-section"></a>En esta sección  
 [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Muestra cómo crear un control compuesto simple en Visual Basic.  
  
 [Tutorial: Crear un control compuesto con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Muestra cómo crear un control compuesto simple en C#.  
  
 [Tutorial: Heredar de un control de Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Muestra cómo crear un control de Windows Forms simple utilizando la herencia en Visual Basic.  
  
 [Tutorial: Heredar de un control de Windows Forms con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Muestra cómo crear un control de Windows Forms simple utilizando la herencia en C#.  
  
 [Tutorial: Realizar tareas comunes utilizando etiquetas inteligentes en controles de Windows Forms](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Muestra cómo usar la característica de etiquetas inteligentes en controles de Windows Forms.  
  
 [Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 Muestra cómo utilizar el <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> atributo para serializar una colección.  
  
 [Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Muestra cómo depurar el comportamiento en tiempo de diseño de un control de Windows Forms.  
  
 [Tutorial: Crear un control de Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 Muestra cómo integrar estrechamente un control compuesto en el entorno de diseño.  
  
 [Cómo: Crear controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Proporciona información general sobre consideraciones para implementar un control de Windows Forms.  
  
 [Cómo: Crear controles compuestos](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 Muestra cómo crear un control al heredar de un control compuesto.  
  
 [Cómo: Heredar de una clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 Proporciona información general sobre el procedimiento para crear un control compuesto.  
  
 [Cómo: Heredar de controles de Windows Forms existentes](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 Muestra cómo crear un control extendido heredando de la <xref:System.Windows.Forms.Button> clase del control.  
  
 [Cómo: Heredar de la clase control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 Proporciona información general sobre la creación de un control extendido.  
  
 [Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Muestra cómo utilizar el <xref:System.Windows.Forms.Control.Dock%2A> propiedad para alinear el control con el borde del formulario que ocupa.  
  
 [Cómo: Mostrar un control en el cuadro de diálogo Seleccionar elementos del cuadro de herramientas](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Muestra el procedimiento para instalar el control de modo que aparezca en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).  
  
 [Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Muestra cómo utilizar el <xref:System.Drawing.ToolboxBitmapAttribute> para mostrar un icono junto al control personalizado en el **cuadro de herramientas**.  
  
 [Cómo: Comprobar el comportamiento de una clase UserControl en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Muestra cómo utilizar **UserControl Test Container** para probar el comportamiento de un control compuesto.  
  
 [Errores en tiempo de diseño en el Diseñador de Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Explica el significado y el uso de la lista de errores de tiempo de diseño que aparece en Microsoft Visual Studio cuando no se puede cargar el Diseñador de Windows Forms.  
  
 [Solución de problemas relacionados con la creación de controles y componentes](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Muestra cómo diagnosticar y corregir los problemas comunes que pueden producirse al crear un componente o control personalizados.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 Describe cómo crear sus propios controles personalizados con .NET Framework.  
  
 [Independencia del lenguaje y componentes independientes del lenguaje](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 Presenta Common Language Runtime, que está diseñado para simplificar la creación y el uso de componentes. Un aspecto importante de esta simplificación es la interoperabilidad mejorada entre los componentes escritos con diferentes lenguajes de programación. Common Language Specification (CLS) hace posible crear herramientas y componentes que funcionen con varios lenguajes de programación.  
  
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Describe cómo habilitar que el componente o el control se muestren en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).
