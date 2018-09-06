---
title: 'Cómo: Aplicar atributos en controles de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 1ab54b0c6828a0648fecfc293b6a7143b012ad6a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43778047"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Cómo: Aplicar atributos en controles de formularios Windows Forms
Para desarrollar componentes y controles que interactúan correctamente con el entorno de diseño y se ejecuten correctamente en tiempo de ejecución, deberá aplicar correctamente los atributos a clases y miembros.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo usar varios atributos en un control personalizado. El control muestra una función de registro simple. Cuando el control se enlaza a un origen de datos, muestra los valores enviados por el origen de datos en un <xref:System.Windows.Forms.DataGridView> control. Si un valor supera el valor especificado por el `Threshold` propiedad, un `ThresholdExceeded` provoca el evento.  
  
 El `AttributesDemoControl` registra valores con un `LogEntry` clase. El `LogEntry` es una clase de plantilla, lo que significa se parametrice en el tipo que registra. Por ejemplo, si la `AttributesDemoControl` es los valores del registro de tipo `float`, cada `LogEntry` instancia se declara y se utiliza como sigue.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Dado que `LogEntry` se parametriza por un tipo arbitrario, debe usar la reflexión para operar en el tipo de parámetro. Para la característica de umbral para que funcione, el tipo de parámetro `T` debe implementar la <xref:System.IComparable> interfaz.  
  
 El formulario que hospeda el `AttributesDemoControl` consulta periódicamente un contador de rendimiento. Cada valor se empaqueta en un `LogEntry` del tipo adecuado y se agrega al formulario <xref:System.Windows.Forms.BindingSource>. El `AttributesDemoControl` recibe el valor mediante su enlace de datos y muestra el valor en un <xref:System.Windows.Forms.DataGridView> control.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 El primer ejemplo de código es el `AttributesDemoControl` implementación. El segundo ejemplo de código muestra un formulario que utiliza el `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Atributos de nivel de clase  
 Algunos atributos se aplican en el nivel de clase. En el ejemplo de código siguiente se muestra los atributos que normalmente se aplican a un control de Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>Atributo TypeConverter  
 <xref:System.ComponentModel.TypeConverterAttribute> es otro atributo de nivel de clase frecuente. En el ejemplo de código siguiente se muestra su uso para el `LogEntry` clase. En este ejemplo también muestra una implementación de un <xref:System.ComponentModel.TypeConverter> para el `LogEntry` tipo, denominado `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Atributos de nivel de miembro  
 Algunos atributos se aplican en el nivel de miembro. Los ejemplos de código siguientes muestran algunos atributos que normalmente se aplican a las propiedades de controles de Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Atributo AmbientValue  
 En el ejemplo siguiente se muestra la <xref:System.ComponentModel.AmbientValueAttribute> y se muestra código que admite su interacción con el entorno de diseño. Se llama a esta interacción *ambiente*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Atributos de enlace de datos  
 Los ejemplos siguientes muestran una implementación de enlace de datos complejo. El nivel de clase <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, como se muestra anteriormente, se especifica la `DataSource` y `DataMember` propiedades que se usará para el enlace de datos. El <xref:System.ComponentModel.AttributeProviderAttribute> especifica el tipo al que el `DataSource` se enlazará la propiedad.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   El formulario que hospeda el `AttributesDemoControl` requiere una referencia a la `AttributesDemoControl` ensamblado con el fin de crear.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Atributos en controles de Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [Cómo: serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
