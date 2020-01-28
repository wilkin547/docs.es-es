---
title: Crear control que muestra el progreso
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: 9d2cf353ba2309380221bb51733baaca1b81a5d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731176"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a>Cómo: Crear un control de formularios Windows Forms que muestre el progreso
En el ejemplo de código siguiente se muestra un control personalizado denominado `FlashTrackBar` que se puede utilizar para mostrar al usuario el nivel o el progreso de una aplicación. Utiliza un degradado para representar visualmente el progreso.  
  
 El control `FlashTrackBar` ilustra los conceptos siguientes:  
  
- Definición de propiedades personalizadas.  
  
- Definición de eventos personalizados. (`FlashTrackBar` define el evento `ValueChanged`).  
  
- Reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A> para proporcionar la lógica para dibujar el control.  
  
- Calcular el área disponible para dibujar el control mediante su <xref:System.Windows.Forms.Control.ClientRectangle%2A> propiedad. `FlashTrackBar` hace esto en el método `OptimizedInvalidate`.  
  
- Implementación de la serialización o persistencia de una propiedad cuando se cambia en el Diseñador de Windows Forms. `FlashTrackBar` define los métodos `ShouldSerializeStartColor` y `ShouldSerializeEndColor` para la serialización de las propiedades `StartColor` y `EndColor`.  
  
 En la tabla siguiente se muestran las propiedades personalizadas definidas por `FlashTrackBar`.  
  
|La propiedad|Descripción|  
|--------------|-----------------|  
|`AllowUserEdit`|Indica si el usuario puede cambiar el valor de la barra de seguimiento flash haciendo clic y arrastrando.|  
|`EndColor`|Especifica el color final de la barra de seguimiento.|  
|`DarkenBy`|Especifica cuánto oscurecer el fondo en relación con el degradado de primer plano.|  
|`Max`|Especifica el valor máximo de la barra de seguimiento.|  
|`Min`|Especifica el valor mínimo de la barra de seguimiento.|  
|`StartColor`|Especifica el color inicial del degradado.|  
|`ShowPercentage`|Indica si mostrar un porcentaje sobre el degradado.|  
|`ShowValue`|Indica si mostrar el valor actual sobre el degradado.|  
|`ShowGradient`|Indica si la barra de seguimiento debe mostrar un degradado de color con el valor actual.|  
|-   `Value`|Especifica el valor actual de la barra de seguimiento.|  
  
 La siguiente tabla muestra los miembros adicionales definidos por el evento de cambio de propiedad `FlashTrackBar:` y el método que genera el evento.  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ValueChanged`|El evento que se genera cuando la propiedad `Value` la barra de seguimiento cambia.|  
|`OnValueChanged`|El método que genera el evento `ValueChanged`.|  
  
> [!NOTE]
> `FlashTrackBar` usa la clase <xref:System.EventArgs> para los datos de evento y <xref:System.EventHandler> para el delegado de eventos.  
  
 Para controlar los eventos *eventName* correspondientes, `FlashTrackBar` reemplaza los siguientes métodos que hereda de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 Para controlar los eventos de cambio de propiedad correspondientes, `FlashTrackBar` reemplaza los siguientes métodos que hereda de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a>Ejemplo  
 El control `FlashTrackBar` define dos editores de tipos de interfaz de usuario, `FlashTrackBarValueEditor` y `FlashTrackBarDarkenByEditor`, que se muestran en los listados de código siguiente. La clase `HostApp` utiliza el control `FlashTrackBar` en un formulario de Windows Forms.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a>Vea también

- [Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Fundamentos de desarrollo de controles de Windows Forms](windows-forms-control-development-basics.md)
