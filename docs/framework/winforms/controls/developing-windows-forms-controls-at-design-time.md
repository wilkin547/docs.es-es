---
title: Desarrollo de controles en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7626e1efbb30ef3bfe9b5b1278c0adb18dd5944b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628714"
---
# <a name="develop-windows-forms-controls-at-design-time"></a>Desarrollar controles Windows Forms en tiempo de diseño

Para los autores de controles, .NET Framework proporciona una gran cantidad de tecnologías de creación de controles. Los creadores ya no están limitados al diseño de controles compuestos que actúan como una colección de controles preexistentes. A través de la herencia, puede crear sus propios controles a partir de controles compuestos preexistentes o de controles de Windows Forms preexistentes. También puede diseñar sus propios controles que implementen el dibujo personalizado. Estas opciones permiten una gran flexibilidad en el diseño y la funcionalidad de la interfaz visual. Para aprovechar estas características, debe estar familiarizado con conceptos de programación basada en objetos.

> [!NOTE]
> No es necesario tener un conocimiento exhaustivo de la herencia, pero puede que le resulte útil hacer referencia a los [conceptos básicos de la herencia (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).

Si quiere crear controles personalizados para usarlos en formularios Web Forms, consulte [Desarrollar controles de servidor ASP.NET personalizados](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).

## <a name="in-this-section"></a>En esta sección

[Tutorial: crear un control compuesto](walkthrough-authoring-a-composite-control-with-visual-csharp.md)\
Muestra cómo crear un control compuesto simple en C#.

[Tutorial: heredar de un Control Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)\
Muestra cómo crear un control de Windows Forms simple utilizando la herencia en C#.

[Tutorial: realizar tareas comunes con las acciones del diseñador](perform-common-tasks-design-actions.md)\
Muestra cómo usar la característica de etiquetas inteligentes en controles de Windows Forms.

[Tutorial: serializar colecciones de tipos estándar con la\ DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)
Muestra cómo usar el atributo <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> para serializar una colección.

[Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)\
Muestra cómo depurar el comportamiento en tiempo de diseño de un control de Windows Forms.

[Tutorial: crear un control de Windows Forms que aprovecha las características en tiempo de diseño de Visual Studio](creating-a-wf-control-design-time-features.md)\
Muestra cómo integrar estrechamente un control compuesto en el entorno de diseño.

[Cómo: Crear controles para Windows Forms](how-to-author-controls-for-windows-forms.md)\
Proporciona información general sobre consideraciones para implementar un control de Windows Forms.

[Cómo: Crear controles compuestos](how-to-author-composite-controls.md)\
Muestra cómo crear un control al heredar de un control compuesto.

[Cómo: Heredar de una clase UserControl](how-to-inherit-from-the-usercontrol-class.md)\
Proporciona información general sobre el procedimiento para crear un control compuesto.

[Cómo: Heredar de controles de Windows Forms existentes](how-to-inherit-from-existing-windows-forms-controls.md)\
Muestra cómo crear un control extendido heredando de la clase de control <xref:System.Windows.Forms.Button>.

[Cómo: Heredar de una clase de control](how-to-inherit-from-the-control-class.md)\
Proporciona información general sobre la creación de un control extendido.

[Cómo: alinear un control con los bordes de los formularios en tiempo de diseño](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)\
Muestra cómo usar la propiedad <xref:System.Windows.Forms.Control.Dock%2A> para alinear el control con el borde del formulario que ocupa.

[Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)\
Muestra el procedimiento para instalar el control de modo que aparezca en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).

[Cómo: proporcionar un mapa de bits del cuadro de herramientas para un Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)\
Muestra cómo utilizar el <xref:System.Drawing.ToolboxBitmapAttribute> para mostrar un icono junto al control personalizado en el cuadro de **herramientas**.

[Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md)\
Muestra cómo utilizar **UserControl Test Container** para probar el comportamiento de un control compuesto.

[Errores en tiempo de diseño en el Diseñador de Windows Forms](design-time-errors-in-the-windows-forms-designer.md)\
Explica el significado y el uso de la lista de errores de tiempo de diseño que aparece en Microsoft Visual Studio cuando no se puede cargar el Diseñador de Windows Forms.

[Solución de problemas relacionados con la creación de controles y componentes](troubleshooting-control-and-component-authoring.md)\
Muestra cómo diagnosticar y corregir los problemas comunes que pueden producirse al crear un componente o control personalizados.

## <a name="reference"></a>Referencia

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a>Secciones relacionadas

[Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)\
Describe cómo crear sus propios controles personalizados con .NET Framework.

[Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md)\
Presenta Common Language Runtime, que está diseñado para simplificar la creación y el uso de componentes. Un aspecto importante de esta simplificación es la interoperabilidad mejorada entre los componentes escritos con diferentes lenguajes de programación. Common Language Specification (CLS) hace posible crear herramientas y componentes que funcionen con varios lenguajes de programación.

[Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)\
Describe cómo habilitar que el componente o el control se muestren en el cuadro de diálogo **Customize Toolbox** (Personalizar cuadro de herramientas).
