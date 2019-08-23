---
title: Procedimiento para aplicar atributos en controles de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 273d32927582f4467a92cd3b8f87e699c1f167d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922784"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Procedimiento para aplicar atributos en controles de formularios Windows Forms
Para desarrollar componentes y controles que interactúen correctamente con el entorno de diseño y se ejecuten correctamente en tiempo de ejecución, debe aplicar correctamente los atributos a las clases y miembros.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar varios atributos en un control personalizado. El control muestra una funcionalidad de registro simple. Cuando el control está enlazado a un origen de datos, muestra los valores enviados por el origen de datos <xref:System.Windows.Forms.DataGridView> en un control. Si un valor supera el valor especificado por la `Threshold` propiedad, se `ThresholdExceeded` genera un evento.  
  
 Registra los valores con una `LogEntry` clase. `AttributesDemoControl` La `LogEntry` clase es una clase de plantilla, lo que significa que se parametriza en el tipo que registra. Por ejemplo, si `AttributesDemoControl` está registrando valores de tipo `float`, cada `LogEntry` instancia se declara y se usa como se indica a continuación.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> Dado `LogEntry` que está parametrizado por un tipo arbitrario, debe usar la reflexión para operar en el tipo de parámetro. Para que la característica de umbral funcione, el tipo `T` de parámetro debe <xref:System.IComparable> implementar la interfaz.  
  
 El formulario que hospeda la `AttributesDemoControl` consulta periódicamente un contador de rendimiento. Cada valor se empaqueta en un `LogEntry` del tipo adecuado y se agrega a la del <xref:System.Windows.Forms.BindingSource>formulario. Recibe el valor a través de su enlace de datos y muestra el valor <xref:System.Windows.Forms.DataGridView> en un control. `AttributesDemoControl`  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 El primer ejemplo de código es `AttributesDemoControl` la implementación de. En el segundo ejemplo de código se muestra un formulario `AttributesDemoControl`que utiliza.  
  
## <a name="class-level-attributes"></a>Atributos de nivel de clase  
 Algunos atributos se aplican en el nivel de clase. En el ejemplo de código siguiente se muestran los atributos que se suelen aplicar a un control de Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter (atributo)  
 <xref:System.ComponentModel.TypeConverterAttribute>es otro atributo de nivel de clase de uso común. En el ejemplo de código siguiente se muestra su `LogEntry` uso para la clase. <xref:System.ComponentModel.TypeConverter> En este ejemplo también se muestra una implementación de para `LogEntry` el tipo, `LogEntryTypeConverter`denominado.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Atributos de nivel de miembro  
 Algunos atributos se aplican en el nivel de miembro. En los siguientes ejemplos de código se muestran algunos atributos que se suelen aplicar a las propiedades de los controles de Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Atributo AmbientValue  
 En el ejemplo siguiente se <xref:System.ComponentModel.AmbientValueAttribute> muestra y se muestra el código que admite su interacción con el entorno de diseño. Esta interacción se denomina *ambiente*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Atributos de DataBinding  
 En los siguientes ejemplos se muestra una implementación de enlace de datos complejo. El nivel <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>de clase, que se mostró anteriormente, especifica `DataMember` las `DataSource` propiedades y que se van a usar para el enlace de datos. Especifica el tipo al que se enlazará la `DataSource` propiedad. <xref:System.ComponentModel.AttributeProviderAttribute>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- El formulario que hospeda el `AttributesDemoControl` requiere una referencia `AttributesDemoControl` al ensamblado para poder compilar.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Desarrollar controles personalizados de Windows Forms con .NET Framework](developing-custom-windows-forms-controls.md)
- [Atributos en controles de Windows Forms](attributes-in-windows-forms-controls.md)
- [Cómo: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
