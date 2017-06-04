---
title: "C&#243;mo: Crear un control de formularios Windows Forms que muestre el progreso | Microsoft Docs"
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
  - "controles [Windows Forms], crear"
  - "controles [Windows Forms], seguimiento del progreso"
  - "control personalizado FlashTrackBar"
  - "progreso, crear informes [Windows Forms]"
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Crear un control de formularios Windows Forms que muestre el progreso
En el ejemplo de código siguiente se muestra un control personalizado denominado `FlashTrackBar` que se puede utilizar para mostrar al usuario el nivel o el progreso de una aplicación.  Utiliza un degradado para representar visualmente el progreso.  
  
 El control `FlashTrackBar` ilustra los siguientes conceptos:  
  
-   Definición de propiedades personalizadas.  
  
-   Definición de eventos personalizados.  \(`FlashTrackBar` define el evento `ValueChanged`\).  
  
-   Reemplazo del método <xref:System.Windows.Forms.Control.OnPaint%2A> para proporcionar lógica para dibujar el control.  
  
-   Cálculo del área disponible para dibujar el control mediante su propiedad <xref:System.Windows.Forms.Control.ClientRectangle%2A>.  `FlashTrackBar` lo realiza en su método `OptimizedInvalidate`.  
  
-   Implementación de la serialización o persistencia de una propiedad cuando se cambia en el Diseñador de Windows Forms.  `FlashTrackBar` define los métodos `ShouldSerializeStartColor` y `ShouldSerializeEndColor` para serializar sus propiedades `StartColor` y `EndColor`.  
  
 En la tabla siguiente se muestran las propiedades personalizadas definidas por `FlashTrackBar`.  
  
|Propiedad.|Descripción|  
|----------------|-----------------|  
|`AllowUserEdit`|Indica si el usuario puede cambiar o no el valor de la barra de seguimiento haciendo clic en ella y arrastrándola.|  
|`EndColor`|Especifica el color final de la barra de seguimiento.|  
|`DarkenBy`|Especifica cuánto hay que oscurecer el fondo con respecto al degradado de primer plano.|  
|`Max`|Especifica el valor máximo de la barra de seguimiento.|  
|`Min`|Especifica el valor mínimo de la barra de seguimiento.|  
|`StartColor`|Especifica el color inicial del degradado.|  
|`ShowPercentage`|Indica si se mostrará o no un porcentaje sobre el degradado.|  
|`ShowValue`|Indica si se mostrará o no el valor actual sobre el degradado.|  
|`ShowGradient`|Indica si la barra de seguimiento debe mostrar o no un degradado de color con el valor actual.|  
|-   `Value`|Especifica el valor actual de la barra de seguimiento.|  
  
 En la tabla siguiente se muestran miembros adicionales definidos por `FlashTrackBar:`, el evento de cambio de propiedades y el método que provoca el evento.  
  
|Miembro|Descripción|  
|-------------|-----------------|  
|`ValueChanged`|El evento que se provoca cuando cambia la propiedad `Value` de la barra de seguimiento.|  
|`OnValueChanged`|El método que provoca el evento `ValueChanged`.|  
  
> [!NOTE]
>  `FlashTrackBar` utiliza la clase <xref:System.EventArgs> para los datos de evento y <xref:System.EventHandler> para el delegado del evento.  
  
 Para controlar los eventos *nombreDeEvento* correspondientes, `FlashTrackBar` invalida los siguientes métodos que hereda de <xref:System.Windows.Forms.Control?displayProperty=fullName>:  
  
-   <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
-   <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 Para controlar los eventos de cambio de propiedades correspondientes, `FlashTrackBar` reemplaza los siguientes métodos que hereda de <xref:System.Windows.Forms.Control?displayProperty=fullName>:  
  
-   <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## Ejemplo  
 El control `FlashTrackBar` define dos editores de tipos de la interfaz de usuario, `FlashTrackBarValueEditor` y `FlashTrackBarDarkenByEditor`, que se muestran en los siguientes listados de códigos.  La clase `HostApp` utiliza el control `FlashTrackBar` en un Windows Form.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## Vea también  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Fundamentos de desarrollo de controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)