---
title: "C&#243;mo: Enlazar a un m&#233;todo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlace, a métodos"
  - "clases, ObjectDataProvider"
  - "enlace de datos, enlazar a métodos mediante ObjectDataProvider"
  - "métodos, enlazar"
  - "ObjectDataProvider (clase)"
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Enlazar a un m&#233;todo
En el ejemplo siguiente se muestra cómo enlazar a un método mediante <xref:System.Windows.Data.ObjectDataProvider>.  
  
## Ejemplo  
 En este ejemplo, `TemperatureScale` es una clase que tiene un método `ConvertTemp`, que toma dos parámetros \(uno de tipo `double` y uno de tipo `enum` `TempType)` y convierte el valor dado de una escala de temperatura a otra.  En el ejemplo siguiente, se utiliza <xref:System.Windows.Data.ObjectDataProvider> para crear instancias del objeto `TemperatureScale`.  Se llama al método `ConvertTemp` con dos parámetros especificados.  
  
 [!code-xml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Ahora que el método está disponible como recurso, puede enlazar sus resultados.  En el ejemplo siguiente, la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> de <xref:System.Windows.Controls.TextBox> y la propiedad <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> de <xref:System.Windows.Controls.ComboBox> se enlazan a los dos parámetros del método.  Esto permite al usuario especificar la temperatura que se desea convertir y la escala de temperatura desde la que efectuar la conversión.  Observe que <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> está establecido en `true` porque estamos enlazando la propiedad <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> de la instancia <xref:System.Windows.Data.ObjectDataProvider> y no las propiedades del objeto contenidas en <xref:System.Windows.Data.ObjectDataProvider> \(el objeto `TemperatureScale`\).  
  
 El <xref:System.Windows.Controls.ContentControl.Content%2A> de la última <xref:System.Windows.Controls.Label> se actualiza cuando el usuario modifica el contenido de <xref:System.Windows.Controls.TextBox> o la selección de <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 El método convertidor `DoubleToString` toma un valor de tipo double y lo convierte en un valor de tipo string en la dirección <xref:System.Windows.Data.IValueConverter.Convert%2A> \(del [origen de enlace](GTMT) al [destino de enlace](GTMT), que es la propiedad <xref:System.Windows.Controls.TextBox.Text%2A>\) y convierte el valor `string` en un valor `double` en la dirección <xref:System.Windows.Data.IValueConverter.ConvertBack%2A>.  
  
 `InvalidationCharacterRule` es una <xref:System.Windows.Controls.ValidationRule> que comprueba si hay caracteres no válidos.  La plantilla de error predeterminada, que es un borde rojo alrededor de un control <xref:System.Windows.Controls.TextBox>, aparece para notificar a los usuarios cuando el valor de entrada no es un valor de tipo double.  
  
## Vea también  
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [Enlazar a una enumeración](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)