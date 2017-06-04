---
title: "C&#243;mo: Aplicar atributos en controles de formularios Windows Forms | Microsoft Docs"
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
  - "atributos [Windows Forms], aplicar"
  - "controles [Windows Forms], aplicar atributos"
  - "controles de Windows Forms, aplicar atributos"
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Aplicar atributos en controles de formularios Windows Forms
Para desarrollar componentes y controles que interactúen correctamente con el entorno de diseño y se ejecuten correctamente en tiempo de ejecución, necesita aplicar correctamente los atributos a las clases y miembros.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar varios atributos en un control personalizado.  El control muestra una función de registro simple.  Cuando el control se enlaza a un origen de datos, muestra los valores enviados por el origen de datos en un control <xref:System.Windows.Forms.DataGridView>.  Si un valor supera el valor especificado por la propiedad `Threshold`, se provoca un evento `ThresholdExceeded`.  
  
 El `AttributesDemoControl` registra los valores con una clase `LogEntry`.  La clase `LogEntry` es una clase de plantilla, que significa que se parametriza en el tipo que registra.  Por ejemplo, si `AttributesDemoControl` está registrando valores de tipo `float`, se declara cada instancia `LogEntry` y se utiliza de la forma siguiente.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Dado que un tipo arbitrario parametriza `LogEntry`, debe utilizar la reflexión para funcionar en el tipo de parámetro.  Para que funcione la característica de umbral, el tipo de parámetro `T` debe implementar la interfaz <xref:System.IComparable>.  
  
 El formulario que hospeda el `AttributesDemoControl` consulta periódicamente un contador de rendimiento.  Cada valor se empaqueta en `LogEntry` del tipo adecuado y se agrega al <xref:System.Windows.Forms.BindingSource> del formulario.  `AttributesDemoControl` recibe el valor a través de su enlace de datos y muestra el valor en un control <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 El primer ejemplo de código es la implementación de `AttributesDemoControl`.  El segundo ejemplo de código muestra un formulario que utiliza `AttributesDemoControl`.  
  
## Atributos de nivel de clase  
 Algunos atributos se aplican en el nivel de clase.  En el ejemplo de código siguiente se muestran los atributos que normalmente se aplican a un control de formularios Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### TypeConverter Attribute  
 <xref:System.ComponentModel.TypeConverterAttribute> es otro atributo de nivel de clase habitualmente utilizado.  En el ejemplo de código siguiente se muestra cómo lo utiliza la clase `LogEntry`.  En este ejemplo también se muestra una implementación de un <xref:System.ComponentModel.TypeConverter> para el tipo `LogEntry`, denominado `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## Atributos de nivel de miembro  
 Algunos atributos se aplican en el nivel de miembro.  En los ejemplos de código siguientes se muestran algunos atributos que se suelen aplicar a las propiedades de los controles de formularios Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### Atributo AmbientValue  
 En el ejemplo siguiente se muestra <xref:System.ComponentModel.AmbientValueAttribute> y muestra código que admite su interacción con el entorno de diseño.  Esta interacción se denomina *ambiente*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### Atributos de enlace de datos  
 En los ejemplos siguientes se muestra una implementación de enlace de datos complejo.  El <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> de nivel de clase, mostrado previamente, especifica las propiedades `DataSource` y `DataMember` que se van a utilizar para el enlace de datos.  <xref:System.ComponentModel.AttributeProviderAttribute> especifica el tipo al que se enlazará la propiedad `DataSource`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## Compilar el código  
  
-   El formulario que hospeda `AttributesDemoControl` requiere una referencia al ensamblado `AttributesDemoControl` para compilarlo.  
  
## Vea también  
 <xref:System.IComparable>   
 <xref:System.Windows.Forms.DataGridView>   
 [Desarrollar controles personalizados de formularios Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Atributos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)